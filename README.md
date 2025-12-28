# 📊 Previsão de Estoque Inteligente com SageMaker Canvas

Este repositório contém a documentação e os resultados do desafio de projeto realizado no bootcamp da **DIO**. O objetivo é prever a demanda de estoque de produtos utilizando o **Amazon SageMaker Canvas**, uma ferramenta de Machine Learning *no-code*.

## 🎯 Objetivos do Projeto

Otimizar a gestão de inventário utilizando modelos preditivos, evitando tanto a falta de produtos (stockout) quanto o excesso de mercadorias paradas.

---

## 🚀 Passo a Passo do Desenvolvimento

### 1. Seleção e Preparação do Dataset

* **Fonte de Dados:** Utilizei o dataset disponível na pasta `datasets`.
* **Limpeza:** Verificação de dados ausentes e formatação de colunas de data (Time Series).
* **Upload:** O arquivo `.csv` foi importado com sucesso para o console do SageMaker Canvas.

### 2. Configuração do Modelo (Build & Train)

Para este modelo de série temporal (Time Series Forecasting), as seguintes configurações foram aplicadas:

* **Coluna Alvo:** `QUANTIDADE_ESTOQUE`.
* **Identificador do Item:** `ID_PRODUTO`.
* **Coluna de Tempo:** `DATA_EVENTO`.
* **Tipo de Treinamento:** *Quick Build*.

### 3. Análise de Performance

Após o treinamento, o SageMaker Canvas forneceu as seguintes métricas (Exemplo):

* **Avg. wQL (Weighted Quantile Loss):** 0.0XX (indica a precisão geral).
* **MAPE (Mean Absolute Percentage Error):** X% de erro médio.
* **RMSE (Root Mean Square Error):** Valor que indica o desvio das previsões.

> **Insight:** Observei que o modelo deu maior peso para a variável `PRECO` e `PROMOCOES` na previsão de demanda.

### 4. Previsão e Resultados

Com o modelo treinado, realizei as previsões:

* **Single Prediction:** Selecionei um produto específico para visualizar sua tendência nos próximos 30 dias.
* **Batch Prediction:** Gerei um arquivo com as previsões de todo o inventário.

**Resultados obtidos:**

* P90 (Cenário otimista): Demanda alta prevista para períodos de feriado.
* P50 (Cenário provável): Estabilidade na maioria dos itens de curva A.
* P10 (Cenário pessimista): Demanda mínima garantida.

---

## 🛠️ Tecnologias Utilizadas

* **AWS SageMaker Canvas:** Construção do modelo de ML sem código.
* **AWS S3:** Armazenamento dos datasets.
* **GitHub:** Documentação e versionamento.

---

## 📈 Conclusão

O uso do SageMaker Canvas mostrou-se extremamente eficiente para gerar previsões de estoque com baixo esforço técnico. O modelo conseguiu identificar padrões sazonais que antes eram tratados de forma manual, permitindo uma tomada de decisão muito mais baseada em dados (Data-Driven).
