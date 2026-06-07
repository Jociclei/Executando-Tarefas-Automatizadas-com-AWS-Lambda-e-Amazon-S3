# Desafio DIO - Executando Tarefas Automatizadas com AWS Lambda e Amazon S3

## Sobre o Projeto

Este projeto foi desenvolvido como parte do laboratório da DIO com o objetivo de consolidar conhecimentos sobre automação de tarefas utilizando AWS Lambda e Amazon S3. A prática permitiu compreender como eventos gerados em um bucket S3 podem acionar funções Lambda para executar processos automaticamente.

## Objetivos

* Compreender o funcionamento do AWS Lambda.
* Utilizar o Amazon S3 como gatilho para automações.
* Criar fluxos automatizados baseados em eventos.
* Aplicar conceitos de computação serverless.
* Documentar os aprendizados obtidos durante o laboratório.

## Serviços Utilizados

### Amazon S3

O Amazon S3 (Simple Storage Service) é um serviço de armazenamento de objetos altamente escalável utilizado para armazenar arquivos, imagens, documentos e outros dados.

### AWS Lambda

O AWS Lambda é um serviço de computação serverless que permite executar código sem a necessidade de gerenciar servidores, sendo acionado por eventos gerados por outros serviços AWS.

## Arquitetura da Solução

Fluxo implementado:

1. Um arquivo é enviado para um bucket S3.
2. O evento de upload dispara automaticamente uma função Lambda.
3. A função processa as informações recebidas.
4. O resultado é armazenado ou registrado conforme a necessidade da aplicação.

### Fluxo Simplificado

```text id="sv5jgi"
Usuário
   │
   ▼
Amazon S3
   │ Evento de Upload
   ▼
AWS Lambda
   │
   ▼
Processamento Automático
```

## Etapas Realizadas

1. Criação do bucket Amazon S3.
2. Configuração dos eventos de notificação.
3. Criação da função AWS Lambda.
4. Definição das permissões IAM necessárias.
5. Associação do gatilho S3 à função Lambda.
6. Testes de upload de arquivos.
7. Validação dos logs no Amazon CloudWatch.

## Exemplo de Código Lambda

```python id="e54owg"
import json

def lambda_handler(event, context):
    print("Arquivo recebido no S3")
    
    return {
        'statusCode': 200,
        'body': json.dumps('Processamento concluído!')
    }
```

## Benefícios Observados

* Automação de tarefas baseada em eventos.
* Eliminação da necessidade de servidores dedicados.
* Escalabilidade automática.
* Redução de custos operacionais.
* Integração simples entre serviços AWS.

## Desafios Encontrados

* Configuração correta das permissões IAM.
* Entendimento da estrutura do evento enviado pelo S3.
* Validação dos logs e tratamento de erros.

## Aprendizados

Durante a prática foi possível compreender como arquiteturas serverless permitem criar aplicações escaláveis e eficientes. A integração entre Amazon S3 e AWS Lambda mostrou-se uma solução poderosa para automatizar processos de forma simples e econômica.

## Evidências

As capturas de tela do laboratório estão disponíveis na pasta `/images`.

### Exemplos

* Criação do bucket S3.
* Configuração do gatilho Lambda.
* Execução da função.
* Logs no CloudWatch.

## Estrutura do Repositório

```text id="qu58i7"
lambda-s3-automation/
│
├── README.md
├── lambda/
│   └── lambda_function.py
├── images/
│   ├── bucket-s3.png
│   ├── lambda-trigger.png
│   ├── lambda-execution.png
│   └── cloudwatch-logs.png
└── docs/
    └── anotacoes.md
```

## Conclusão

Este laboratório permitiu consolidar conhecimentos sobre computação serverless e automação baseada em eventos na AWS. A utilização conjunta do Amazon S3 e AWS Lambda demonstrou uma abordagem moderna, eficiente e escalável para processamento automático de dados.

## Autor

Projeto desenvolvido como atividade prática da formação AWS na DIO.
