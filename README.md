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

3. Verificar se o contêiner está em execução:

   ```bash
   docker ps

![image](https://github.com/user-attachments/assets/8eb4ebe3-42a7-4570-85d3-ea641ef5eabb)
   
4. Configurar as credenciais da AWS:

   ```bash
   aws configure

![image](https://github.com/user-attachments/assets/165475d1-630d-4326-bf8e-e7cdb26bf870)

5. Verificar se a mensagem esta em fila:
   
   ```bash
    aws --endpoint-url=http://localhost:4566 sqs receive-message --queue-url http://sqs.us-east-1.localhost.localstack.cloud:4566/000000000000/fila --max-number-of-messages 1 --wait-time-seconds 10

![image](https://github.com/user-attachments/assets/b0e3d3c8-96a2-4aa6-be51-45260cce7331)

6. Por fim consumir pelo programa java:

![image](https://github.com/user-attachments/assets/709dc626-a16e-4f61-a2ad-70e5713417c5)

