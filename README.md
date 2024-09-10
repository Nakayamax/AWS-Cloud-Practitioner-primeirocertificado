# AWS-Cloud-Practitioner -  Primeiro certificado AWS

Olá Seja bem vindo(a)!


## INTRODUÇÃO - CLOUD AWS 

O que é a nuvem? O conceito de nuvem pode parecer abstrato, mas trata-se de uma rede de data centers espalhados pelo planeta. A computação em nuvem refere-se ao fornecimento de recursos computacionais, como servidores, bancos de dados, armazenamento e outros serviços de TI, através da internet. Esses serviços são oferecidos por plataformas como AWS, Google Cloud e Microsoft Azure.

A computação em nuvem possibilita utilizar recursos de infraestrutura como serviço (IaaS), plataforma como serviço (PaaS) e software como serviço (SaaS), sem a necessidade de investir em hardware físico e outros componentes tradicionais. Isso permite que você tenha seu sistema funcionando com menos recursos, de forma personalizada e pagando apenas pelo que utilizar.

As nuvem conta com 3 serviços essenciais.

Iaas - Oferta recursos computacionais :

 ![image](https://github.com/user-attachments/assets/68cf786f-3c44-4b21-bc39-89fd5640a13d)






Paas - Oferta plataforma de desenvolvimento



![image](https://github.com/user-attachments/assets/21594379-3077-4002-ae4a-a8a929c18892)





Saas - Oferta plicações prontas para uso via internet


![image](https://github.com/user-attachments/assets/2bc9a503-0ea6-438f-a86f-b72bcafc9ba0)

------------------------------------------------------------------------------------





![image](https://github.com/user-attachments/assets/6ed11f28-fe6b-4221-ad76-1ff60c6abb3f)

Mais próximo de IaaS: Maior complexidade no gerenciamento de provedores, pois você lida com mais componentes da 
infraestrutura.

Mais próximo de PaaS: Menos complexidade do gerenciamento, pois você se concentra em aplicações e a plataforma é 
gerida pelo provedor.

Mais próximo de SaaS: Menor complexidade no gerenciamento, pois o provedor cuida de tudo, e você apenas utiliza 
o software.



Integração do serviço da AWS com o Athena

![image](https://github.com/user-attachments/assets/0a02d273-7ee4-4223-a39c-7b0ac59ef257)

Visão Geral do Amazon Athena
Amazon Athena é um serviço interativo de consultas SQL que facilita a análise de dados diretamente no Amazon S3. Ele elimina a necessidade de processos complexos de ETL (extração, transformação e carregamento) e paga apenas pelas consultas executadas.

Benefícios

Sem Servidor: Não há necessidade de configurar e gerenciar servidores.
Paga Apenas pelas Consultas: Cobre apenas pelas consultas executadas.
Resultados Rápidos: A maioria dos resultados é retornada em segundos e processa grandes conjuntos de dados com facilidade.
Fluxo simplificado de integração 

Armazenar Dados - exemplo de uso !

Amazon S3: Coloque seus dados no Amazon S3 em formatos como CSV, JSON, Parquet, etc.
Definir o Esquema

AWS Glue (opcional): Use um Glue Crawler para catalogar os dados e definir o esquema. Alternativamente, defina o esquema manualmente no Athena.
Amazon Athena: Crie uma tabela no Athena que aponta para o local dos dados no S3.
Consultar Dados

Amazon Athena: Use SQL para consultar dados diretamente no S3. Exemplos de SQL:
sql
Copiar código
[SELECT * FROM tableName WHERE columnName = 'value';]

Visualização de Resultados: Os resultados são exibidos no Editor de Consultas do Athena e podem ser exportados como arquivos CSV.
Integrações com Outros Serviços da AWS

AWS CloudTrail: Consulte logs de atividades da AWS.
Application Load Balancer: Analise logs de tráfego e desempenho.
Amazon VPC: Investigue logs de tráfego de rede e padrões de uso.
Passos para Configuração no Amazon Athena
Criar um Bucket no Amazon S3:

Carregue seus dados no S3.
Definir o Esquema:

Navegue até o Amazon Athena no Console AWS.
Crie um banco de dados e uma tabela usando SQL, apontando para o bucket do S3.
Exemplo de comando SQL para criar uma tabela:

sql
Copiar código
CREATE EXTERNAL TABLE IF NOT EXISTS nome_da_tabela (
    coluna1 tipo,
    coluna2 tipo
    ...
)
ROW FORMAT DELIMITED
FIELDS TERMINATED BY ','
STORED AS TEXTFILE
LOCATION 's3://bucket-nome/pasta/';
Executar Consultas SQL:

No Editor de Consultas do Athena, escreva e execute consultas SQL.
Integrações:

CloudTrail: Crie uma tabela para logs de CloudTrail e consulte diretamente no Athena.
Application Load Balancer: Crie uma tabela para logs e consulte para analisar o tráfego.
Amazon VPC: Crie uma tabela para logs de fluxo e analise padrões de tráfego de rede.
