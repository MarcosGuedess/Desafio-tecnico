# Desafio-tecnico

## Descrição

O projeto foi criado para ser usado como um teste para uma posição de Engenheiro de Dados e envolve o uso de serviços da AWS como S3, Athena e bibliotecas Python (awswrangler, boto3, pyathena) para lidar com tarefas de ingestão e análise de dados. O código lê arquivos CSV, insere dados em um bucket S3 no formato Parquet, cria tabelas correspondentes no Amazon Athena e realiza consultas SQL para análise de dados de acordo com perguntas de negócios.

## Tabela de Conteúdos

- [Requisitos](#requisitos)
- [Configuração](#configuração)
- [Estrutura AWS](#estrutura-aws)
- [Relacionamentos](#relacionamentos)
- [Relacionamentos](#relacionamentos)
- [Questões de SQL Desenvolvidas](#Questões-de-SQL-Desenvolvidas)

## Requisitos
- AWS account e serviços: S3, Athena
- Bibliotecas Python: `pandas`, `pyathena`, `awswrangler`, `boto3`, `os`, `dotenv`

## Configuração.
- Crie dois Bucket no S3 => um para receber os dados (CSV) e outro para salvar as consultas realizadas no Athena. 
- Configure as variáveis de ambiente para as credenciais da AWS (AWS_ACCESS_KEY, AWS_SECRET_KEY, AWS_REGION, etc.) dentro do arquivo ```.env``` .
- Crie um database dentro do Athena com o seguinte comando SQL : ``` CREATE DATABASE <NOME DO SEU DATABASE>;``` que seja idêntico ao nome do bucket que aramazenará os dados CSV.

- **OBS** Verifique se todos os ambientes na AWS foram configurados na mesma região.

## Estrutura AWS

<p align="center">
  <img src="https://github.com/MarcosGuedess/Desafio-tecnico/blob/main/images/pipeline.drawio.png" width="400">
</p>


### S3 Buckets

Certifique-se de ter um S3 Bucket criado com o nome desejado, a região e se o bucket permite acesso externo.

### Amazon Athena
O Amazon Athena utiliza o mecanismo de consulta do Presto para permitir consultas SQL em dados armazenados no Amazon S3, facilitando a análise de dados sem a necessidade de configurar e gerenciar infraestrutura de banco de dados.

# Scripts
Siga as instruções de código em [main.ipynb](https://github.com/MarcosGuedess/Desafio-tecnico/blob/main/main.ipynb).

É importante que você salve suas informações de usuário em variáveis de ambiente usando a biblioteca dotenv.

https://sparkbyexamples.com/python/using-python-dotenv-load-environment-variables/

Também é necessário habilitar suas chaves de acesso e secretas da AWS para usá-las com as bibliotecas Boto3 (para inserir dados e acessar S3 buckets) e Pyathena (para consultar dados).

https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html

O script carregará arquivos .csv como dataframes Pandas e, em seguida, os inserirá no S3 Bucket desejado, criando uma nova tabela Athena para consulta para cada .csv individualmente, como na imagem abaixo:

<p align="center">
  <img src="https://github.com/MarcosGuedess/Desafio-tecnico/blob/main/images/athena.png" width="400">
</p>




# Relacionamentos
Modelo conceitual dos dados:

<p align="center">
  <img src="https://github.com/MarcosGuedess/Desafio-tecnico/blob/main/images/MER.png" width="400">
</p>


## Questões de SQL Desenvolvidas 
- As resoluções dos desafios encontram-se dentro do darquivo [main.ipynb](https://github.com/MarcosGuedess/Desafio-tecnico/blob/main/main.ipynb).
