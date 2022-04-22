# **/SEMANTIX_ACADEMY**
## **/PROJETO_SPARK // CAMAPNHA NACIONAL DE VACINAÇÃO CONTRA COVID-19**
 - **/ALUNO:** FELIPE CHAGAS DE SOUZA
 - **/TREINAMENTO:** BIG DATA ENGINEER 

Este projeto contém a solução para o desafio bônus do treinamento Big Data Engineer disponibilizado pela Semantix Academy.

## **Ambiente em que a solução foi desenvolvida:**
- Cluster Docker Big Data com base no cluster criado pelo @fabiogjardim
  + [Link para o github do Fábio Jardim](https://github.com/fabiogjardim/bigdata_docker)
  + HDFS
  + Spark
  + Kafka
  + Elasticsearch
  + Hive
  + Jupyter Notebook (PySpark)

- Versões do Ambiente:
  + Spark: 2.4.1
  + Scala: 2.11.12
  + Hadoop: 2.7.4
  + Elastic: 7.9.2

## **SOLUÇÃO NÍVEL BÁSICO**

Escopo da Solução Nível Básico disponível no arquivo em files/escopo_projeto_final_spark.pdf:
- [Link para Acesso ao Escopo do Nível Básico](https://github.com/chagasfelipe/semantix_spark_covid_challenge/blob/main/files/escopo_projeto_final_spark.pdf)

A solução foi realizada em um Jupyter Notebook com PySpark, o arquivo está localizado no diretório solution_notebooks/:
+ [link do notebook solução nível básico](https://github.com/chagasfelipe/semantix_spark_covid_challenge/blob/main/solution_notebooks/solucao_spark_nivel_basico.ipynb).

### **Requisitos para quem deseja reproduzir a solução:**
- Docker 
- Docker Compose
- unrar (Instalar no Container Spark)

### **Passos para inciar o ambiente:**
+ Nota: meu ambiente foi com WSL2
- Baixar o projeto no diretório desejado:
```python
git clone https://github.com/chagasfelipe/semantix_spark_covid_challenge.git
```
- Acessar o diretório /source:
```python
$ cd source
```
- Para o funcionamento do Elasticsearch, setar vm.max_map_count:
```python
$ sudo sysctl -w vm.max_map_count=262144
```
- Importar bibliotecas parquet-hadoop e elasticsearch-spark para o container do spark:
```python
$ docker cp libs/parquet-hadoop-bundle-1.6.0.jar spark:/opt/spark/jars
$ docker cp libs/elasticsearch-spark-20_2.11-8.1.3.jar spark:/opt/spark/jars
```
- Iniciar o cluster Big Data com o docker-compose:
```python
$ docker-compose up -d
```

-Acessar o container Docker do Spark:
```python
$ docker exec -it spark bash
```

- Instalar o unrar e atualizar o Requests:
```python
$ apt-get update
$ apt install unrar-free
$ pip install --upgrade requests
$ pip install rarfile
```

- Validar se o Elasticsearch está no ar:
 + Elasticsearch: http://localhost:9200/
 + Kibana: http://localhost:5601/

- Acessar o Jupyter Spark http://localhost:8889/
  + Importar o arquivo solucao_spark_nivel_basico.ipynb localizado na pasta solution_notebooks:
    + [Link do solucao_spark_nivel_basico.ipynb](https://github.com/chagasfelipe/semantix_spark_covid_challenge/blob/main/solution_notebooks/solucao_spark_nivel_basico.ipynb).


### **Acesso WebUI dos Frameworks**
- HDFS:  http://localhost:50070
- Kafka Manager: http://localhost:9000
- ElasticSearch (Kibana): http://localhost:5601
- Jupyter Spark: http://localhost:8889/
