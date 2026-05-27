# observabilidade_opentelemetry
Esta repositório contém os arquivos e diretórios utilizados no laboratório de observabilidade que usa Prometheus, Loki, OpenTelemetry, Jaeger e Grafana para a monitoração de uma aplicação Spring.
Cada um dos elementos de observabilidade foi executado em container docker, dentro de uma máquina virtual do VirtualBox Linux Ubnuntu server:

alex@ubuntusrv:~/lab-otel/eclipse-workspace/ambiente-tracing$ docker ps -a
CONTAINER ID   IMAGE                                    COMMAND                  CREATED          STATUS                             PORTS                                             NAMES
26c1d285cfab   kdpsc/alura:client-api-cursos            "/scripts/client.sh"     43 seconds ago   Up 26 seconds                                                                        client-api-cursos
1afc56bcbac4   jaegertracing/opentelemetry-all-in-one   "/go/bin/opentelemet…"   43 seconds ago   Up 29 seconds                      0.0.0.0:16686->16686/tcp, [::]:16686->16686/tcp   jaeger-api-cursos
d67fb14f346e   otel/opentelemetry-collector:latest      "/otelcol --config=/…"   43 seconds ago   Up 32 seconds                      4317-4318/tcp, 55679/tcp                          collector-api-cursos
6c4925004ea9   grafana/loki                             "/usr/bin/loki -conf…"   43 seconds ago   Up 34 seconds                      3100/tcp                                          loki-api-cursos
22a27beb2c8e   grafana/grafana                          "/run.sh"                44 seconds ago   Up 36 seconds                      0.0.0.0:3000->3000/tcp, [::]:3000->3000/tcp       grafana-api-cursos
932af03c20e9   prom/prometheus:latest                   "/bin/prometheus --c…"   44 seconds ago   Up 37 seconds                      0.0.0.0:9090->9090/tcp, [::]:9090->9090/tcp       prometheus-api-cursos
714046c385b6   proxy-api-cursos                         "/docker-entrypoint.…"   44 seconds ago   Up 39 seconds                      0.0.0.0:80->80/tcp, [::]:80->80/tcp               proxy-api-cursos
dd4b8d81a0bc   api-cursos                               "/__cacert_entrypoin…"   44 seconds ago   Up 40 seconds (health: starting)   8080/tcp                                          api-cursos
6b067b844d27   redis                                    "docker-entrypoint.s…"   45 seconds ago   Up 41 seconds                      6379/tcp                                          cache-api-cursos
7b9e5ddadc42   kdpsc/alura:database-api-cursos          "docker-entrypoint.s…"   45 seconds ago   Up 41 seconds (healthy)            5432/tcp                       
