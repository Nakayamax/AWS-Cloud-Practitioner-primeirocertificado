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


_________________________________________________________________________________________________________________________________________________________________________________________________________________

O Que São Tags?

Tags são rótulos que você adiciona aos recursos da AWS (como instâncias EC2) para organização e gerenciamento. Cada tag tem uma chave e um valor (por exemplo, Ambiente=Produção).

Características das Tags
Atribuição:

Só pode adicionar tags depois que o recurso é criado.
Chaves e valores de tags diferenciam maiúsculas de minúsculas.
Tags com prefixo aws: são automáticas e não podem ser alteradas ou removidas.
Você pode adicionar até 50 tags por recurso.

Tags Comuns:

Exemplos: Ambiente (produção, teste), Aplicativo, Departamento, Centro de Custos.
Ferramentas de Gerenciamento:

AWS Config: Verifica se as tags necessárias estão aplicadas.
IAM Policies: Força o uso de tags específicas quando você cria recursos.


Práticas Recomendadas

Tags Relevantes: Crie tags que ajudem a organizar e gerenciar seus recursos.

Consistência: Use um formato padrão para suas tags.

Automatização: Utilize ferramentas para gerenciar e pesquisar tags automaticamente.

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Gerenciamento de custos e práticas recomendadas

![image](https://github.com/user-attachments/assets/17133fee-d223-492e-9d1d-cdd8384a3f90)


Gerenciamento e Otimização de Custos na AWS
Definir Orçamentos Personalizados:

Crie orçamentos para monitorar e controlar seus gastos.
Ajuste seus recursos para se adequar ao que você realmente precisa.
Escolher Instâncias Apropriadas:

Instâncias T2/T3: Boas para cargas de trabalho com desempenho intermitente.
Instâncias Reservadas: Economize ao se comprometer com instâncias de longa duração.
Instâncias Spot: Use para tarefas temporárias e obtenha descontos significativos.
Considerar Modelos de Computação Sem Servidor:

AWS Lambda: Pague apenas pelo tempo de computação usado e evite custos de servidores ociosos.
Usar Serviços Gerenciados:

Amazon RDS e S3: Reduza custos operacionais com serviços que não exigem gerenciamento contínuo.
Utilizar o AWS Trusted Advisor:

Receba recomendações para reduzir custos, melhorar desempenho e segurança.
Encontrar e Eliminar Desperdícios:

Amazon CloudWatch: Monitore a utilização dos recursos e identifique os ociosos.
AWS Cost Explorer: Analise os custos por projeto e descubra onde economizar.
Automatizar o Gerenciamento de Recursos:

Stopinator: Use scripts para automatizar o desligamento de instâncias não usadas fora do horário de trabalho.
Ferramentas e Serviços de Custo:

AWS Bills: Detalhes das suas faturas.
AWS Cost Explorer: Visualize e analise seus custos.
AWS Budgets: Defina e monitore seus orçamentos.
AWS Cost and Usage Reports: Relatórios detalhados de uso e custo.
AWS Trusted Advisor: Receba conselhos para otimizar custos e desempenho.

![image](https://github.com/user-attachments/assets/4295b873-6fbf-4741-b9bc-6d0f296cbffa)


AWS Cost Explorer

Visualizar Dados: Veja seus gastos dos últimos 13 meses.
Previsão de Gastos: Estime quanto você pode gastar nos próximos 3 meses.
Recomendações de Instâncias: Receba sugestões sobre quais instâncias reservadas comprar para economizar.
Faturamento Consolidado: Se você usa várias contas, pode ver os custos de todas elas em um só lugar, com detalhes diários e mensais por conta.



![image](https://github.com/user-attachments/assets/7d8194fa-a92b-4f7a-ae62-23c59e6a3c3c)

>> O script Stopinator é uma ferramenta usada para parar instâncias do Amazon EC2 em um determinado horário ou com base em certas condições. A seguir, apresento um guia simplificado sobre como usar o Stopinator.

O que é o Stopinator?
Stopinator é um script que automatiza o processo de parada de instâncias do EC2. Ele pode ser configurado para parar instâncias em horários específicos, com base em tags, ou outras condições definidas pelo usuário. É útil para economizar custos e gerenciar instâncias que não precisam estar em execução o tempo todo.

Aws trusted advisor > verificar 




-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



Estratégia de construção da AMI


![image](https://github.com/user-attachments/assets/e6cfc6e5-541a-4217-a16f-aabe5ac95649)

O que é uma AMI?
AMI (Amazon Machine Image) é uma imagem de máquina fornecida pela AWS que contém todas as informações necessárias para iniciar uma instância do Amazon EC2 (Elastic Compute Cloud).

Componentes da AMI:

Sistema Operacional: O sistema operacional (por exemplo, Linux ou Windows) que será executado na instância.

Aplicações e Configurações: Software, aplicativos e configurações pré-instaladas que você deseja na instância.

Dados: Dados e arquivos necessários para a operação da aplicação ou serviço.

Funcionalidade:

Iniciar Instâncias: Você usa uma AMI para criar e iniciar novas instâncias do EC2 com a configuração especificada.

Consistência e Reutilização: Permite criar várias instâncias com a mesma configuração inicial, facilitando a escalabilidade e a replicação de ambientes.
Criação e Gerenciamento:

Criação:

Você pode criar uma AMI a partir de uma instância existente, que inclui o sistema operacional, software e configurações. Isso pode ser feito através do Console da AWS, AWS CLI, ou API.

Cópia:

AMIs são específicas para a região onde foram criadas. Se você precisar usar a AMI em outra região, é necessário copiá-la para essa nova região.

Criptografia:

Se sua AMI contém dados sensíveis, você pode criptografar os volumes de armazenamento (snapshots) associados.

Custos:

Snapshots: Quando uma AMI é criada, ela gera snapshots dos volumes de armazenamento, e você será cobrado pelo armazenamento desses snapshots até que você exclua a AMI.

Uso de AMIs:

Instâncias Idênticas: Se você precisa de várias instâncias com a mesma configuração, você pode lançar novas instâncias a partir da AMI.

Escalabilidade: AMIs facilitam o aumento da capacidade e a replicação de ambientes, garantindo que todas as instâncias iniciadas tenham uma configuração idêntica.

Exemplo Prático:

Se você configurar um servidor web com uma aplicação e deseja criar várias instâncias desse servidor, você pode criar uma AMI dessa instância configurada. Sempre que precisar de uma nova instância com a mesma configuração, você simplesmente inicia uma instância EC2 a partir dessa AMI.

Em resumo, uma AMI é uma ferramenta crucial para criar e gerenciar instâncias EC2, oferecendo uma maneira eficiente de padronizar e replicar ambientes na AWS.




-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Modelos de inicialização do Amazon EC2

O que é um Modelo de Inicialização?

Um Modelo de Inicialização é um recurso no Amazon EC2 que armazena configurações para iniciar instâncias. Ele facilita e padroniza a criação de novas instâncias com as mesmas configurações.

Principais Componentes:

Configurações Armazenadas:

ID da Imagem de Máquina da Amazon (AMI)
Tipo de instância (ex.: t2.micro)
Sub-rede
Par de chaves
Grupo de segurança (opcional)

Benefícios:

Simplificação: Armazena todas as configurações de inicialização para que você não precise especificá-las toda vez que iniciar uma nova instância.

Gerenciamento Eficiente: Facilita o uso com EC2 Auto Scaling, Spot Fleet, Instâncias Spot e Sob Demanda.

Consistência: Ajuda a implementar padrões e práticas recomendadas, reduzindo erros e melhorando a segurança.

Redução de Custos: Ajuda a controlar e gerenciar melhor os custos.

Versões do Modelo de Inicialização:

Versões: Você pode criar várias versões de um modelo de inicialização. Cada versão pode ter diferentes configurações.

Versão Padrão: Por padrão, a primeira versão do modelo é usada, mas você pode definir qualquer versão como padrão.

Escolha da Versão: Ao iniciar uma instância, você pode escolher qual versão do modelo usar.

Exemplo de Uso:

Criar um Modelo: Defina as configurações, como o tipo de instância e a AMI.

Criar Versões: Atualize as configurações em novas versões conforme necessário.

Inicializar Instâncias: Use o modelo de inicialização para criar instâncias com as configurações predefinidas.

Resumo Final: Modelos de Inicialização facilitam a criação e a gestão de instâncias do EC2, garantindo consistência e eficiência ao definir e reutilizar configurações.



----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Infraestrutura como código

Infraestrutura como Código (IaC)
Objetivo: Aprender sobre infraestrutura como código (IaC) e como ela ajuda a gerenciar recursos de forma eficiente.

O que é IaC?

Infraestrutura como Código (IaC) é uma prática que usa código para automatizar o provisionamento e gerenciamento de recursos de infraestrutura.

Benefícios:

Consistência e Confiabilidade: Garante que a infraestrutura seja provisionada de forma repetível e consistente.

Redução de Erros: Minimiza erros manuais e diferenças na configuração.

AWS CloudFormation:

O que é?: 

Um serviço da AWS que permite criar e gerenciar recursos de infraestrutura usando arquivos de template em código.

Usos:

Criar ambientes idênticos para testes ou recuperação.

Reduzir custos criando e destruindo ambientes temporários.

Gerenciamento de Configuração:

Após o Provisionamento: Após a infraestrutura ser criada, você precisa gerenciar configurações e fazer atualizações.
Ferramentas:

AWS Systems Manager: Automatiza tarefas e gerencia a configuração de forma centralizada.

AWS OpsWorks for Chef Automate: Fornece uma solução para automação de configuração e gerenciamento de recursos.

Principais Pontos:

Use IaC para automatizar o provisionamento de recursos de forma confiável.

O AWS CloudFormation é uma ferramenta chave para IaC na AWS.

Após o provisionamento, utilize ferramentas como AWS Systems Manager e AWS OpsWorks para gerenciar e configurar a infraestrutura.

Resumo: IaC permite a automação e consistência no gerenciamento de infraestrutura, com o AWS CloudFormation facilitando a criação de recursos. Para gerenciar configurações após a criação, utilize o AWS Systems Manager e o AWS OpsWorks.


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Introdução ao JSON e ao YAML


JSON:

Mais detalhado, com chaves e aspas.
Menos legível por humanos comparado ao YAML.
Amplamente usado e fácil de analisar.
YAML:

Mais legível por humanos com menos sintaxe detalhada.
Suporta comentários e é mais fácil de depurar.
Usa recuo para estruturar dados e é menos verboso.
Esses formatos são usados para armazenar e manipular dados, com YAML oferecendo uma abordagem mais amigável para leitura humana e JSON sendo mais comum em sistemas de computador. Ambos são compatíve


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



