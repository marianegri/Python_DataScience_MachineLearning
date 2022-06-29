# Gerência De Infraestrutura Para Big Data
## Big Data
É um termo bastante utilizado atualmente e diretamente ligado ao volume de dados a ser capturado, processado e analisado

## Data Science
Prática que envolve métodos científicos, processos e sistemas para extrair conhecimento de dados

## HADOOP
Framework que auxilia no processamento distribuído de datasets em clusters e que utiliza modelos simples de programação
Ecossistema, conjunto de ferramentas.

## Cluster
Um cluster consiste em computadores fortemente ligados que trabalham em conjunto, arquitetura distribuida.\
Atividades de bigdata:
- Instalação , manutenção e suporte
- Ingestão e transformação dos dados
- Analise e geração de insights

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
~~~
