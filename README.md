# NLP Sentiment Analysis with Spark

**Análise de Sentimentos em Avaliações de Filmes usando PySpark e NLP**

Este projeto utiliza o PySpark para realizar uma análise de sentimentos em avaliações de filmes em português. O conjunto de dados utilizado é o [IMDB Reviews em Português](https://www.kaggle.com/datasets/luisfredgs/imdb-ptbr), que contém avaliações de filmes com rótulos de sentimentos (positivo/negativo). O projeto abrange desde a limpeza e pré-processamento dos dados até a construção de um modelo de classificação usando Árvore de Decisão.

## Tabela de Conteúdos

- [Instalação](#instalação)
- [Uso](#uso)
- [Estrutura do Projeto](#estrutura-do-projeto)
- [Resultados](#resultados)
- [Contribuição](#contribuição)
- [Licença](#licença)

## Instalação

Para executar este projeto, você precisará ter o PySpark instalado. Você pode instalar as dependências necessárias usando o seguinte comando:

!pip install pyspark


## Uso

**Configuração do Spark:**

from pyspark.sql import SparkSession

spark = SparkSession.builder \
    .master('local[*]') \
    .appName("analise_nlp") \
    .getOrCreate()

**Leitura dos dados**
dados = spark.read.csv("/content/imdb-reviews-pt-br.csv",
                       escape="\"",
                       header=True,
                       inferSchema=True)


**Análise Exploratória:**

Contagem de linhas e colunas.

Visualização do esquema.

Exibição de amostras de comentários.

**Limpeza e Pré-processamento:**

Remoção de caracteres especiais.

Tokenização.

Remoção de stopwords.

Geração de Bag of Words e TF-IDF.

**Modelagem:**

Construção de um pipeline de transformação.

Treinamento de um modelo de Árvore de Decisão.

Avaliação do modelo usando métricas de acurácia.

## Estrutura do Projeto
nlp-sentiment-analysis-spark.ipynb: Notebook do Google Colab contendo todo o código e análises.

imdb-reviews-pt-br.csv: Conjunto de dados utilizado para a análise.

## Resultados
O modelo de Árvore de Decisão alcançou uma acurácia de aproximadamente 70% na classificação dos sentimentos das avaliações. A análise exploratória revelou que os dados estão balanceados, com uma proporção quase igual de comentários positivos e negativos.
