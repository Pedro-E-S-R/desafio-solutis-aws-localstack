# desafio-solutis-aws-localstack

# Configuração do LocalStack com Docker e AWS

Este guia fornece um passo a passo sobre como configurar o LocalStack usando Docker e AWS CLI para simular serviços da AWS, como o SQS, e integrá-los a uma aplicação Java.

## Pré-requisitos

- **Docker**: Certifique-se de que o Docker esteja instalado e em execução em sua máquina.
- **AWS CLI**: Instale a AWS Command Line Interface (CLI) na sua máquina.
- **Java**: Tenha o JDK instalado para compilar e executar o código Java.

## Passo 1: Executar o LocalStack no Docker

1. Abra um terminal ou PowerShell.
2. Execute o seguinte comando para iniciar o LocalStack em um contêiner Docker:

   ```bash
   docker run --name localstack -d -p 4566:4566 localstack/localstack
