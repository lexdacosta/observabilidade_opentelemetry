# observabilidade_opentelemetry

Introdução

Observabilidade Distribuída com OpenTelemetry, Jaeger, Grafana, Prometheus e Loki

Este é um projeto baseado no curso [Rastreamento:
Fazendo tracing com Jaeger e OpenTelemetry] ministrado pelo professor @kleber-costa na Alura.
Cada um dos elementos de observabilidade foi executado em container docker, dentro de uma máquina virtual do VirtualBox Linux Ubnuntu server:

O objetivo deste laboratório é o de simular uma arquitetura distribuída instrumentada, permitindo analisar métricas, logs e traces em uma aplicação Spring Boot executando em containers Docker, integrados com ferramentas modernas de observabilidade.

Durante o desenvolvimento foram implementados:

- Tracing distribuído com OpenTelemetry
- Instrumentação automática da aplicação Java
- Coleta de métricas e logs
- Proxy reverso instrumentado com NGINX
- Visualização de traces no Jaeger
- Dashboards e métricas no Grafana
- Monitoração via Prometheus
- Centralização de logs
- Simulação de tráfego com cliente sintético

O ambiente foi construído com foco em aprendizado prático de conceitos modernos de SRE, Observabilidade e troubleshooting em sistemas distribuídos.

Componentes Utilizados

Desenvolvimento da Aplicação
- Eclipse IDE
- Java
- Spring Boot
- Maven
- Banco de Dados e Cache
- PostgreSQL
- Redis

Observabilidade
- OpenTelemetry
- OpenTelemetry Collector
- Jaeger
- Prometheus
- Grafana
- Loki

Infraestrutura e Containers
- Docker
- Docker Compose
- NGINX (Proxy Reverso)

Simulação e Testes
- Cliente sintético para geração de tráfego
- APIs REST instrumentadas

Arquitetura Geral do Projeto

O fluxo do ambiente ocorre da seguinte forma:

- A aplicação Spring Boot recebe requisições HTTP
- O NGINX atua como proxy reverso instrumentado
- O OpenTelemetry instrumenta a aplicação Java automaticamente
- Os traces são enviados ao OpenTelemetry Collector
- O Jaeger recebe e exibe os traces distribuídos
- O Prometheus coleta métricas do ambiente
- O Grafana consolida dashboards e visualizações
- O Loki centraliza logs para troubleshooting
- O cliente sintético gera tráfego e simula consumo da aplicação

Sequência de Construção do Ambiente
1. Criação da aplicação
Desenvolvimento da API Spring Boot no Eclipse
Criação de endpoints REST
Integração com banco PostgreSQL
Configuração inicial da aplicação
2. Containerização
Criação do Dockerfile
Criação do docker-compose
Subida inicial dos containers
3. Banco de dados e cache
Configuração do PostgreSQL
Configuração do Redis
Integração da aplicação com os serviços
4. Instrumentação OpenTelemetry
Configuração do Java Agent do OpenTelemetry
Instrumentação automática da aplicação
Configuração do OpenTelemetry Collector
5. Tracing distribuído
Integração com Jaeger
Visualização dos spans e traces
Identificação do fluxo distribuído das requisições
6. Monitoração
Configuração do Prometheus
Criação de métricas
Integração com Grafana
Construção de dashboards
7. Logs centralizados
Integração de logs da aplicação
Configuração do Loki
Visualização e troubleshooting via Grafana
8. Proxy reverso instrumentado
Configuração do NGINX
Instrumentação do NGINX com OpenTelemetry
Visualização dos spans do proxy no Jaeger
9. Simulação de tráfego
Execução de cliente sintético
Geração de carga
Simulação de erros e troubleshooting
Dificuldades Encontradas

Durante o desenvolvimento do laboratório, diversos desafios técnicos e problemas de compatibilidade foram encontrados, principalmente devido à integração entre múltiplas ferramentas de observabilidade modernas.

Compatibilidade entre versões

Algumas versões do OpenTelemetry Collector, Java Agent, Jaeger e Grafana apresentaram incompatibilidades entre si, exigindo ajustes e alinhamento de versões.

Instrumentação do NGINX

A instrumentação do NGINX exigiu configuração específica de módulos e ajustes de integração com o OpenTelemetry.

Troubleshooting de traces

Em determinados momentos os traces não apareciam corretamente no Jaeger devido a problemas de exportação, configuração do Collector e endpoints incorretos.

Integração entre logs e métricas

Foi necessário ajustar formatos de logs e labels para correta integração entre Loki, Grafana e Prometheus.

Configuração de containers

Problemas relacionados a networking Docker, resolução de nomes e comunicação entre containers exigiram ajustes no docker-compose.

Compatibilidade de bibliotecas Java

Algumas dependências da aplicação Spring Boot exigiram atualização para correta instrumentação automática via OpenTelemetry Java Agent.

Simulação de falhas

Foram realizados testes interrompendo containers e serviços para validar tracing, logs, métricas, troubleshooting e identificação de gargalos no ambiente.

Objetivos do Laboratório
- Aprender conceitos modernos de Observabilidade
- Estudar tracing distribuído
- Praticar troubleshooting em ambientes distribuídos
- Compreender os pilares da observabilidade
- Simular cenários reais de incidentes
- Desenvolver habilidades relacionadas a SRE e Reliability Engineering

A infraestrutura:
<img width="1106" height="350" alt="image" src="https://github.com/user-attachments/assets/97a6fdf3-fe0f-4557-afb3-906cde4e002c" />

A API:
<img width="1364" height="190" alt="image" src="https://github.com/user-attachments/assets/29310080-1d97-4984-8952-ca417d48f1ac" />

As métricas:
<img width="1366" height="382" alt="image" src="https://github.com/user-attachments/assets/1f7c5c98-9eb7-4c26-965a-54bdf4a6154d" />

Targets no prometheus:
<img width="1362" height="543" alt="image" src="https://github.com/user-attachments/assets/b394bf2f-263e-467c-9019-4ffa76d8ca4f" />

Dashboards no Grafana:
<img width="1332" height="687" alt="image" src="https://github.com/user-attachments/assets/b1f18bcf-3bac-46a1-9d16-ef454b2451b3" />

<img width="1315" height="497" alt="image" src="https://github.com/user-attachments/assets/7a883108-072c-475d-abc2-4560661390a0" />

<img width="1323" height="543" alt="image" src="https://github.com/user-attachments/assets/ed3c4599-2d6f-495d-804b-8d244c7c0c35" />

Exemplo de tracing distribuído no Jaeger:
<img width="1344" height="683" alt="image" src="https://github.com/user-attachments/assets/979f6b6e-41c8-41a3-8eab-36c676e442c7" />

Créditos

Este laboratório foi desenvolvido com base em estudos práticos sobre Observabilidade, OpenTelemetry e tracing distribuído ministrados no curso já mencionado.

O ambiente foi expandido com experimentações adicionais envolvendo:

- instrumentação de aplicações Java
- tracing distribuído
- monitoração
- troubleshooting
- dashboards
- logs centralizados
- proxy reverso instrumentado
- troubleshooting distribuído
