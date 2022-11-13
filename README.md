# desafio-DIO-Explorando-Dados-Demograficos-com-Servicos-de-Big-Data-na-AWS

Este repositório traz os passos para usar o serviço da AWS para subir os dados e fazer pesquisas por Query.

# Passo 1: Criar bucket no Amazon S3

  Vamos no Amazon S3 Console -> Buckets -> Create bucket -> Bucket name [dio-live-athena-gcbiotec] - Create bucket
  Create folder (Criei uma pasta chamada /output e outra com o nome do seu conjunto de dados. Este nome irá definir o nome da tabela criada no Glue) e finalmente realizei Upload dos arquivos de dados localizados na pasta /data do material de apoio

# Passo 2: Criar Glue Crawler - um serviço que faz a leitura automática dos campos da tabela

    1)Vamos em Amazon Glue Console -> Crawlers -> Add Crawler
    2)Seguimos algumas configurações recomendadas: Source type [Data Stores] -> Crawl all folders; Data store [S3] -> Include path [caminho do diretório dos dados de entrada]; Create IAM Role; Frequency [Run on demand]; Database name [database-exercicio-athena-dio]; Group behavior [Create a single schema for each S3 path]; Finish; Databases -> Tables -> Visualizar dados das tabelas criadas
    
    
  <img src="print crawler.png"
  alt="Alt text"
  title="Optional title"
  style="display: inline-block; margin: 0 auto; max-width: 300px">
    
 # Passo 3: Criar aplicação no Amazon Athena - usado para fazer as pesquisas nas tabelas que foram geradas pelo Crawler

    Query editor -> Settings -> Manage settings -> Query result location and encryption -> Browse S3 -> selecionar o bucket criado
    Selecionar Database -> criar queries (exemplos na pasta /src)
    Verificar queries não salvas no bucket criado no S3
    Salvar queries -> Executar novamente -> Verificar no bucket criado no S3
    
 # Passo 4: Criando nova tabela

    Generate table DDL
    Copiar a query gerada
    Selecionar o DB e criar a nova tabela em uma nova query
   
 # Passo 5: Visualizar dados no Amazon QuickSight

    Signup (caso não tenha conta) -> Escolher [Standard]
    Datasets -> Create new dataset -> Athena -> Name [NomeDoDataSet] -> Create
    Select database -> select table -> Edit or preview -> Save & visualize
    Criar visualizações selecionando colunas, criando filtros e parâmetros e selecionando Visual types para gráficos.
  
