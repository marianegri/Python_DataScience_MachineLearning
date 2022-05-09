# Banco de dados
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

### P: Consistência 

## Não relacionais - NOSQL - sem esquema
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
* 
