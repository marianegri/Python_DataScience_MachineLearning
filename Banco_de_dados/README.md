# Banco de dados
Sistema de Gerência de Banco de Dados - SGDB
 - CRUD : Create (criar), Read(ler), Update(atualizar), Delete(deletar)
 
## Histórico
* 1959 : Linguagem COBOL (alto nível) direcionada a aplicações do mercado financeiro

## Big Data
* 6 V's : Volume, velocidade, variedade, validade, volatividade, valência
* Volume variedade e velocidade aumentam muito, e para ajudar com isso usa-se o banco de dados NOSQL

### Clusters
Juntar equipamentos de baixo custo a milheres.
Grupo de computadpres que trabalham em rede de forma coordenada.
Cada computador é um "nodo" do cluster
**Paralelismo**

## Teorema CAP

### C : Consistência
Não há divergencia de versões.
Propagação muito rápida da versão atual para todos os nodos

### A: disponibilidade do serviço

### P: Persistencia 

## Relacionais - SQL - Com esquema prévio
Modelo de Dados: 
**Chaves primárias artificiais**
- Físico, 
- Lógico
   - modelo de um banco de dados relacional,
   - Chave estrangeira se relaciona com chave primária,
   - Restrição de Integridade,
   - Ex:. Tabelas (colunas, dados adicionados)
- Conceitual 
   - Nível mais alto de abstração, 
   - utilizado nas etapas iniciais de projeto,
   - Identificador,
   - Caradinalidade,
   - autoralacionamento Ex:. Diciplica = pre requisito (relac)
   - Generalização/Especialização (Herança): modelo lógico não tem conhecimento de herança (utilizar chave estrangeira para criar a relação de herança **ou** tabela que abranja toda a hierarquia **ou** criar as tabelas especializadas, apenas as folhas da hierarquia),
   - Entidade Associativa (Para quando queremos associar 3 tabelas num mesmo relacionamento), 
   - Ex:. Entidade-Relacionamento
Conceitos:
* Formas Normais
* Propriedades ACID
* Transações
* Linguagem SQL: Linguagem padronizada
  * DDL: Data Definition Language : CREATE, DROP, ALTER
  * DML: Data Manipulation Language: INSERT, DELETE, UPTADE
* Consulta :  SELECT, INNER JOIN - Junção interna , OUTER JOIN - Junção externa (LEFT, RIGHT, FULL)
  * (JUNÇÃO CONDICIONAL (_ON_), EQUIJUNÇÃO (NOMES IGUAIS - _USING_), JUNÇÃO NATURAL (_NATURAL JOIN_)) 
* GROUP BY :  UTILIZAR : COUNT(*), COUNT(EXPRESSÃO), AVG, MIN, MAX

## Não relacionais - NOSQL - sem esquema prévio
### Chave Valor:
 * Base de implementação dos outros BD
 * Valor pode ser qualquer tipo de dado (inclusive outro conjunto de pares chave-valor)
   - Atributo do tipo escalar: possui apenas um valor, numero, timestamp, texto, binário (texto compactado, dados criptografados, imagem), boleano, colunas nulas não são armazenadas
   - Atributo do tipo documento: semi-estruturados (semelhando JASON)
   - Mapa: armazena pares de chave-valor
   - Conjunto : armazena dados de apenas o mesmo tipo (vetores)
 * Chave primária (obrigatória) e chave de ordenação (não obrigatória)
 * Particionamento (separar por grupos) e replicação (colocar em locais diferentes para ter segurança)
 * Alta velocidade : Aplicação em IoT
 * Alta capacidade escalar
 * Economico
 * Contras: funcionalidade limitadas, não lidam nativamente com estrutura de dados, só efetua querys pela chave ou indice
 * Mais famosos: **Amazon DynamoDB**, **LinkedIn Voldemort**, **Redis**

#### Ignate apache
* Ansi SQL
* In-memory
* Bibliotecas de ML

#### DYNAMODB

### Banco colunar (Column Family):
* Exemplo de uso: Google Earth 
* valor contem nome da familia de coluna e deus atributos
* Não armazena valores nulos
* Campos tem tempo de vida (bom para dados voláteis)

#### Cassandra
* Dados imutáveis (insere novos valores, não faz alteração), gravação rápida.
* Persistencia temporaria
* Compactação: tirar o exesso de registros que não servem mais
* Muito tipado, usuário pode definir tipos

### Grafos
#### [Minimum Spanning Tree](https://github.com/marianegri/Minimum_Spanning_Tree)
