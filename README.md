# Automarizando tarefas com Lambda e S3
## Entendendo o Amazon S3
O Amazon S3 (Simple Storage Service) é um serviço de armazenamento em nuvem que permite armazenar e acessar dados de forma segura, durável e escalável. Ele suporta qualquer tipo de arquivo e é amplamente utilizado para backup, armazenamento de objetos e distribuição de conteúdo.

As principais vantagens do S3 incluem:
-Durabilidade: alta confiabilidade e redundância, garantindo proteção contra falhas e perda de dados.
-Disponibilidade: acesso contínuo aos dados em qualquer momento e local.
-Escalabilidade: ajuste automático da capacidade de armazenamento conforme a demanda.
-Segurança: oferece criptografia, controle de acesso e monitoramento detalhado das operações.

## Entendendo o AWS Lambda
O AWS Lambda é um serviço de computação serverless que permite executar código em resposta a eventos, sem a necessidade de provisionar ou gerenciar servidores. Basta enviar o código e o Lambda se encarrega de executá-lo automaticamente, ajustando os recursos conforme a demanda.

As principais vantagens de utilizar o Lambda são:
-Execução sob demanda: o código é executado automaticamente em resposta a eventos específicos.
-Escalabilidade automática: o serviço ajusta a capacidade conforme o número de requisições.
-Custo-benefício: a cobrança é feita apenas pelo tempo de execução e quantidade de solicitações.
-Integração com outros serviços AWS: como S3, DynamoDB, API Gateway e CloudWatch, permitindo automações completas e eficientes.

## Tarefas com Lambda e S3
Exemplo de projeto: Upload de arquivo com processamento e registro no DynamoDB

Este desafio tem como objetivo criar uma arquitetura automatizada que processa arquivos enviados para o Amazon S3, utilizando o AWS Lambda para gerenciar o fluxo e o DynamoDB como banco de dados de registro.

O fluxo funciona da seguinte forma:

O usuário realiza o upload de um arquivo em um bucket S3.

Esse evento dispara automaticamente uma função Lambda escrita em Python.

A função Lambda processa o conteúdo do arquivo (por exemplo, leitura de dados ou formatação) e grava as informações em uma tabela do Amazon DynamoDB.

Uma segunda função Lambda pode ser configurada para consultar a tabela e expor os dados processados por meio de uma API criada no Amazon API Gateway.

<img width="435" height="758" alt="Diagrama sem nome drawio (1)" src="https://github.com/user-attachments/assets/9fb8aa5a-a302-4911-a4da-c7c0838e94a2" />

O diagrama acima ilustra a arquitetura da solução, demonstrando como cada serviço interage para garantir o processamento, validação e exposição dos dados de forma automatizada e escalável.

Testes locais com LocalStack

Para o desenvolvimento e testes desse projeto, foi utilizado o LocalStack, uma ferramenta que simula localmente os serviços da AWS, permitindo validar toda a arquitetura sem custos de execução na nuvem. Isso facilita o processo de desenvolvimento, depuração e integração, garantindo que as funções Lambda e as interações com o S3 e o DynamoDB funcionem corretamente antes da implantação real na AWS.
