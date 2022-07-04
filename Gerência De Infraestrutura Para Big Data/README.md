# Gerência De Infraestrutura Para Big Data
## Big Data
- É um termo bastante utilizado atualmente e diretamente ligado ao volume de dados a ser capturado, processado e analisado.
- Além de armazenar e processar é preciso extrair valor.
- Grande volume em relação ao sistema de processamento.
- Dados estruturados e não estruturados.
- Contem diferentes padrões de dados para serem analisados.
- Maquinas geram mais dados que as pessoas (leitires de RFID, sensores, gps)
- Necessário extrair valor
- Dimensões do Big data : guerra dos V's: 
    - 3V's: ``Volume``, ``Velocidade`` (rapidez com que os dados chegam), ``variedade`` (classificação de dados: estruturados e não estruturados), 
    - 4V's: ``veracidade`` (tem incerteza sobre os dados, separar para conseguir dados uteis e reais), 
    - 6V's (MicroSoft): ``variabilidade`` (Os padrões podem variar), ``visibilidade``, 
    - 5V's: ``valor`` (Manter apenas o que traz valor, até quando traz valor?, dados sem ser processados não trazem valor)

## Data Science
Prática que envolve métodos científicos, processos e sistemas para extrair conhecimento de dados

## Abordagens Tradicionais para armazenamento de dados
- Os trabalhos em lote são programados para migrar dados para **Data Warehouse** em um período de dia, semana ou mês
- Os dados têm um esquema e são categorizados como dados estruturados
- Eles passam por um ciclo de análise para criar conjuntos de dados e extrair informações significativas
- Ingestão no Data Warehouse são realizadas por meio de operações ETL (Extract, Transform, and Load) - pega dados brutos e processa-os para relatórios e análises
- Data Warehouse é otimizado somente para relatórios e análise de dados
- Sistema principal de Bussines Intelligence (BI)
- Problemas:
  - Latência (dados não são em tempo real)
  - Fontes limitadas (depende de dados estruturados)
  - Escala Limitada: **scale-up** (estou com problema de velocidade compro maquina mais rapida)


## Cluster
Um cluster consiste em computadores fortemente ligados que trabalham em conjunto, arquitetura distribuida.\
Características de um cluster computing:
- Alta Disponibilidade: Várias maquinas, caso uma falhe as outras continuam (com um pouco menos de capacidade de processamento)
- Fácil escalabilidade: **scale-out**, aumenta a capacidade de recursos adicionando mais computadores
- Processamento paralelo
- Hardware de commodity : componentes de prateleira, utilização de hardwares tradicionais com mais baixo custo

### Infraestrutura
 - Local (on-premises)
 - Nuvem

Atividades de bigdata:
- Instalação , manutenção e suporte
- Ingestão e transformação dos dados
- Analise e geração de insights


## HADOOP
Plataforma de armazenamento e processamento de dados
Grandes volumes de dados
Framework que auxilia no processamento distribuído de datasets em clusters e que utiliza modelos simples de programação
Ecossistema, conjunto de ferramentas.
- Localidade de dados
- Dividir para conquistar (shared nothing)
### Arquitetura HADOOP
- Cluster YARN : Processamento
    - Conceitos basicos: modelo mestre-escravo (ResourseManager (principal) e NodeManager(secundário) e AppliccationMaster (responsavel pela aplicação do cluster))
- Cluster HDFS : Armazenamento
    -   Conceitos basicos: Muitas ferramentas são em JAVA, modelo mestre-escravo, sistema de aquivos(64 ou 128 MB por bloco, os blocos são distribuidos entre os compuatdores e replicaodos para caso algum falhe seja processado em outra maquina) (Nó principal - NameNode: gerencia os meta dados) (Nó secundário - DataNode)

- Cluster HADOOP : Combina os clusters HDFS e YARN rodando nas mesmas maquinas. Na mesma maquina tem processo pra gerenciar os blocos localmente e outro processo para gerenciar as tarefas que estão processando em cima daqueles blocos.

### Modos de implantação do cluster HADOOP
- LocalJobRunner: sistemas de arquivos local: Utilizado para teste, identificar bugs, n utiliza HDFS, simula ambiente hadoop
- PseudoDistribuido: Toda a arquitetura vista acima ocorre na mesma maquina. Simula como um cluster completo funciona
- Totalmente Distribuido





## Scala
Linguagem de programação de propósito geral. Type-safe.
~~~scala
val nome_variavel = "PUC"   // val é imutavel

var nao_variavel = "PUC"   // var é mutável
nao_variavel += "RS"

// Definindo o tipo das variaveis
var exemplo1:String = "PUC"
var d = 1.234
var f = 1.344f
var c:Char = 'm'

// Defininndo funções
def multiplicador(value:int): int = {
  if( value % 2 == 0){   // Se o numero for PAR multiplica por 2
    return value*2
  } else{
    return value*3
  }
}
// Chamando funções
multiplicador(10)

// Split em caractere duplo (.txt para data frame)
al movdf = spark.read.text("/user/maria/movies.dat")
val movies_df = movdf.rdd.map(r => r.mkString.split("::")).map{case Array(a, b, c) => (a, b, c)}.toDF("Id", "titulo", "genero")
// Para poder usar SQL
movies_df.createOrReplaceTempView("movies")
// Utilizando SQL
spark.sql("select * from movies").show(false)

// Repartição
mr.coalesce(1).write.mode("overwrite").parquet("/user/maria/movierating2")  // trafego na rede otimizado
mr.repartition(1).write.mode("overwrite").parquet("/user/maria/movierating2")
~~~
