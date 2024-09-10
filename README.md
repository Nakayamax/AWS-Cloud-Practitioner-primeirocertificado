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

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

>> Jumpstart no AWS Advanced


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


![image](https://github.com/user-attachments/assets/ba5382f6-abcc-4219-bf93-ab95dade3ed1)

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


Observação : AMAZON S3 X BUCKET : 

![image](https://github.com/user-attachments/assets/ffffc252-d2a4-4636-9f11-9b062c5740a7)

Bucket no Amazon S3

Um bucket é um contêiner dentro do Amazon S3 onde os dados são armazenados. É o nível mais alto de organização no Amazon S3 e é usado para organizar os dados de forma hierárquica.

DADOS X OBJETO 

Dados: O conteúdo real, como um arquivo, imagem, ou vídeo.

Objeto: É a unidade básica de armazenamento no Amazon S3. 

Cada objeto tem três partes:

Metadados: Informações sobre o objeto, como tipo de arquivo e data de criação.
Chave: Um nome único para identificar o objeto no bucket.
Bucket: É como uma pasta no Amazon S3 onde você armazena objetos.Cada bucket pode conter muitos objetos.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

AWS Organizations

![image](https://github.com/user-attachments/assets/0472d0ee-f0ed-43d4-91ac-2a8c980a8696)

AWS Organizations: Visão Geral Simplificada
O que é o AWS Organizations?
O AWS Organizations é um serviço que permite gerenciar várias contas da AWS de forma centralizada. Ele oferece funcionalidades para controle de faturamento e políticas de acesso, facilitando a administração em ambientes com muitas contas.

Estrutura Básica

Raiz: Ponto de partida da organização.

Unidades Organizacionais (UOs): Grupos de contas que podem incluir subgrupos, formando uma estrutura hierárquica.

Contas: Elementos individuais que podem estar em UOs ou diretamente na raiz.

##Funcionalidades Principais

Gerenciamento de Contas: Crie e gerencie contas novas ou existentes a partir da conta principal.
Faturamento Consolidado: Visualize um resumo das cobranças de todas as suas contas em um único lugar.
Políticas de Controle de Serviço (SCPs): Defina e aplique regras sobre o que cada conta ou grupo de contas pode ou não fazer com os serviços da AWS.


Benefícios

Controle Centralizado: Defina políticas de acesso e uso de serviços de maneira centralizada.

Automação: Crie e gerencie contas de forma automática.

Visão Unificada: Obtenha uma visão consolidada das cobranças de todas as contas.

Segurança e Controle

IAM (Identity and Access Management): Gerencia o acesso a serviços e recursos dentro de uma conta específica.

SCPs (Service Control Policies): Regula o acesso a serviços em uma ou mais contas dentro de uma UO.


CASO DE USO


![image](https://github.com/user-attachments/assets/844b9aa8-c888-4321-8859-bdcd6d24f7aa)

Descrição do Fluxo

Início: Começa com a conta principal.

Criar Organização: Crie a organização com a conta principal.

Adicionar Contas: Adicione novas contas ou convide contas existentes.

Criar UOs: Organize as contas em unidades organizacionais (UOs).

Definir e Aplicar SCPs: Configure políticas de controle de serviço.

Gerenciar e Monitorar: Revise o faturamento consolidado e teste as políticas.

Usar Interfaces de Gerenciamento:

Console da AWS: Interface web.

AWS CLI: Linha de comando.

SDKs: Bibliotecas de programação.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



![image](https://github.com/user-attachments/assets/70b5ef65-e9bf-4a2a-a76d-41e049df36bd)


>> AWS CloudTrailA

AWS CloudTrail é um serviço que registra e monitora continuamente as atividades na sua conta AWS. Ele captura chamadas de API, atividades do Console de Gerenciamento da AWS e da AWS CLI, e envia esses logs para armazenamento, geralmente no Amazon S3.

Funcionalidades Principais

Registro de Atividades: Captura chamadas de API e ações realizadas via Console e AWS CLI.

Compatibilidade: Suporta muitos serviços AWS.

Armazenamento de Logs: Envia logs automaticamente para o Amazon S3 após configuração.

Limitações: Não rastreia eventos dentro de instâncias EC2, como desligamentos manuais.

Exemplo de Uso
Perguntas Frequentes: Quem encerrou uma instância? Quem alterou a configuração de um grupo de segurança? Há atividades suspeitas de IPs desconhecidos?

Análise de Logs: Armazene logs em um bucket do S3 e analise-os para responder a questões de segurança e conformidade.


![image](https://github.com/user-attachments/assets/8456a4c8-8d7a-4bd4-a5d6-91369a7fcd4f)


Diagrama Simplificado do AWS CloudTrail


Criar Bucket S3: Onde os logs serão armazenados.

Definir Trilha: Configuração dos tipos de eventos a serem registrados.

Configurar SNS (Opcional): Notificações quando novos logs são entregues.

Configurar CloudWatch Logs (Opcional): Monitoramento e alarmes para logs.

Ativar Criptografia (Opcional): Proteção dos logs armazenados.

Registro e Armazenamento:

Registrar Atividades: O CloudTrail captura ações e chamadas de API.

Enviar Logs para S3: Armazenamento seguro dos logs no bucket S3.

Análise de Logs:

Examinar Logs no S3: Revisão dos logs armazenados para análise.

Monitorar com CloudWatch (Opcional): Monitoramento em tempo real.

Receber Notificações SNS (Opcional): Alertas sobre novos logs.

