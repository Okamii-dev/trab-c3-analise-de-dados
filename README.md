# Análise de Dados e Machine Learning — House Prices

Projeto desenvolvido para a disciplina de **Análise de Dados**, com o objetivo de explorar o dataset **House Prices: Advanced Regression Techniques**, do Kaggle, aplicando etapas de análise exploratória, tratamento de dados, engenharia de características, modelos supervisionados e técnicas não supervisionadas.

O estudo busca compreender quais características dos imóveis mais influenciam o preço de venda e como diferentes técnicas de Machine Learning podem ser utilizadas para prever, classificar, agrupar e interpretar padrões presentes nos dados.

---

### Integrantes

* Alexsander Amorim Borchardt
* Ester da Silva Bertolani
* Larissa Moraes de Jesus
* Lucas Rufino Gonçalves de Souza
* Marcelo Henrique Fortaleza Mindas
* Vanderson de Almeida Alves

---

## Descrição do projeto

Este projeto utiliza um conjunto de dados de imóveis residenciais dos Estados Unidos, contendo informações sobre área construída, qualidade geral, localização, garagem, porão, ano de construção, quantidade de cômodos e outras variáveis relacionadas às propriedades.

A variável principal analisada é `SalePrice`, que representa o preço de venda dos imóveis.

A partir dessa base, foram realizadas as seguintes etapas:

- Análise exploratória dos dados;
- Identificação de variáveis numéricas e categóricas;
- Tratamento de valores ausentes;
- Engenharia de características;
- Modelagem supervisionada para regressão;
- Modelagem supervisionada para classificação binária;
- Aplicação de técnicas não supervisionadas;
- Avaliação dos modelos por métricas;
- Visualização e interpretação dos resultados.

---

## Objetivo

O objetivo principal do projeto é aplicar um fluxo completo de análise de dados e Machine Learning para investigar os fatores que influenciam o preço de venda de imóveis.

Entre os objetivos específicos estão:

- Explorar a distribuição dos preços dos imóveis;
- Identificar variáveis com maior correlação com `SalePrice`;
- Tratar valores ausentes e preparar os dados para modelagem;
- Construir modelos de regressão para prever o preço de venda;
- Criar uma classificação binária para separar imóveis de preço alto e baixo;
- Agrupar imóveis com características semelhantes;
- Reduzir a dimensionalidade dos dados para visualização;
- Identificar possíveis outliers no conjunto de dados;
- Comparar os resultados obtidos com diferentes métricas.

---

## Estrutura do repositório

```text
TRAB-C3-ANALISE-DE-DADOS/
│
├── Data-Analysis-and-Machine-Learning-Notebook.ipynb
├── README.md
├── requirements.txt
│
├── data/
│   ├── train.csv
│   ├── test.csv
│   └── sample_submission.csv
│
└── docs/
    ├── Avaliação_C3 - Data Analysis and Machine Learning Hackathon - 2023_1.pdf
    └── data_description.txt
```

### Descrição dos principais arquivos

| Arquivo/Pasta | Descrição |
|---|---|
| `Data-Analysis-and-Machine-Learning-Notebook.ipynb` | Notebook principal do projeto, contendo a análise, os modelos, as métricas e as visualizações. |
| `data/train.csv` | Base de treino utilizada nas análises e na modelagem. |
| `data/test.csv` | Base de teste disponibilizada junto ao dataset original. |
| `data/sample_submission.csv` | Arquivo de exemplo de submissão do Kaggle. |
| `docs/data_description.txt` | Dicionário de dados com a descrição das variáveis do dataset. |
| `docs/Avaliação_C3 - Data Analysis and Machine Learning Hackathon - 2023_1.pdf` | Enunciado da atividade proposta. |

---

## Etapas desenvolvidas

### 1. Análise Exploratória de Dados — EDA

A primeira etapa teve como objetivo compreender a estrutura do dataset e analisar o comportamento da variável alvo `SalePrice`.

Foram realizadas análises como:

- Dimensão do dataset;
- Estatísticas descritivas da variável `SalePrice`;
- Distribuição dos preços dos imóveis;
- Assimetria e curtose da variável alvo;
- Matriz de correlação entre variáveis numéricas;
- Relação entre preço, área habitável e qualidade geral;
- Análise de variáveis categóricas relevantes, como bairro e qualidade externa.

Essa etapa permitiu identificar padrões importantes, como a influência da qualidade geral, da área construída, da garagem, do porão e da localização sobre o preço final dos imóveis.

---

### 2. Feature Engineering

Na etapa de engenharia de características, os dados foram preparados para os modelos de Machine Learning.

As principais ações realizadas foram:

- Tratamento de valores ausentes;
- Preenchimento de variáveis categóricas com valores adequados;
- Preenchimento de variáveis numéricas;
- Validação da ausência de valores nulos após o tratamento;
- Codificação de variáveis categóricas;
- Preparação das variáveis independentes e da variável alvo.

Também foi aplicada transformação logarítmica na variável `SalePrice`, com o objetivo de reduzir a assimetria da distribuição e melhorar o desempenho dos modelos de regressão.

---

### 3. Aprendizagem Supervisionada — Regressão

Para prever diretamente o preço de venda dos imóveis, foi utilizado um modelo de **Regressão Linear**.

As métricas utilizadas para avaliação foram:

- **MAE** — Mean Absolute Error;
- **RMSE** — Root Mean Squared Error;
- **R² Score** — coeficiente de determinação.

Resultado obtido com o modelo de Regressão Linear:

| Métrica | Resultado |
|---|---:|
| MAE | 16.325,21 |
| RMSE | 25.085,21 |
| R² | 0,9180 |

O resultado indica que o modelo conseguiu explicar uma parte significativa da variação dos preços dos imóveis.

---

### 4. Aprendizagem Supervisionada — Classificação

Além da previsão direta do preço, também foi criada uma tarefa de classificação binária.

A variável `SalePrice` foi convertida em duas classes:

- **Preço baixo**;
- **Preço alto**.

O limiar utilizado foi a mediana dos preços, no valor aproximado de **US$ 163.000,00**.

Foram comparados os seguintes modelos:

- Regressão Logística;
- Árvore de Decisão;
- Random Forest.

O melhor desempenho foi obtido pelo modelo **Random Forest**.

| Modelo | Accuracy | Precision | Recall | F1-score |
|---|---:|---:|---:|---:|
| Random Forest | 0,9247 | 0,9366 | 0,9110 | 0,9236 |
| Árvore de Decisão | 0,8767 | 0,8716 | 0,8836 | 0,8776 |
| Regressão Logística | 0,8664 | 0,8591 | 0,8767 | 0,8678 |

---

### 5. Aprendizagem Não Supervisionada

Na etapa não supervisionada, foram aplicadas técnicas para identificar padrões internos nos dados sem utilizar diretamente a variável alvo como resposta.

#### Clusterização com KMeans

O algoritmo **KMeans** foi utilizado para agrupar imóveis com características semelhantes.

Foram testadas diferentes quantidades de clusters, e o melhor valor encontrado pelo **Silhouette Score** foi:

```text
k = 2
```

Distribuição dos imóveis por cluster:

| Cluster | Quantidade de imóveis |
|---|---:|
| 0 | 823 |
| 1 | 637 |

A análise dos clusters indicou a formação de grupos com diferenças em características como preço médio, área habitável, qualidade geral, ano de construção, tamanho do porão e quantidade de vagas na garagem.

---

#### Redução de dimensionalidade com PCA

A técnica **PCA — Principal Component Analysis** foi utilizada para reduzir os dados para duas dimensões e permitir uma visualização geral da estrutura dos imóveis.

Resultado da variância explicada:

| Componente | Variância explicada |
|---|---:|
| PC1 | 6,53% |
| PC2 | 3,18% |
| Total acumulado | 9,71% |

Mesmo com baixa variância acumulada em apenas dois componentes, o PCA auxiliou na visualização dos agrupamentos e da distribuição geral dos registros.

---

#### Análise de outliers com LOF

Para identificação de imóveis atípicos, foi utilizado o algoritmo **Local Outlier Factor — LOF**.

Resultado encontrado:

| Categoria | Quantidade |
|---|---:|
| Registros normais | 1.387 |
| Outliers | 73 |

A técnica permitiu destacar imóveis com combinações incomuns de características em relação ao restante da base.

---

## Comparação dos modelos de regressão

Além da Regressão Linear, também foram comparados modelos baseados em árvore para a tarefa de regressão.

| Modelo | MAE | RMSE | R² |
|---|---:|---:|---:|
| Regressão Linear | 16.325,21 | 25.085,21 | 0,9180 |
| Random Forest | 17.456,37 | 29.144,45 | 0,8893 |
| Árvore de Decisão | 23.364,42 | 33.813,39 | 0,8509 |

A Regressão Linear apresentou o melhor desempenho geral entre os modelos avaliados para regressão.

---

## Tecnologias e bibliotecas utilizadas

O projeto foi desenvolvido em **Python**, utilizando **Jupyter Notebook**.

Principais bibliotecas:

- `pandas`;
- `numpy`;
- `matplotlib`;
- `seaborn`;
- `scipy`;
- `scikit-learn`.

Principais técnicas e algoritmos:

- Regressão Linear;
- Regressão Logística;
- Árvore de Decisão;
- Random Forest;
- KMeans;
- PCA;
- Local Outlier Factor;
- Métricas de regressão;
- Métricas de classificação;
- Visualização de dados.

---

## Como executar o projeto

### 1. Clone o repositório

```bash
git clone https://github.com/Okamii-dev/trab-c3-analise-de-dados.git
```

### 2. Acesse a pasta do projeto

```bash
cd trab-c3-analise-de-dados
```

### 3. Instalação das dependências

Para instalar as bibliotecas necessárias, execute:

```bash
pip install -r requirements.txt
```

### 4. Abra o notebook

Você pode executar o projeto em:

- Jupyter Notebook;
- JupyterLab;
- Google Colab;
- VS Code com extensão Jupyter.

Arquivo principal:

```text
Data-Analysis-and-Machine-Learning-Notebook.ipynb
```

### 5. Execute as células em ordem

Para garantir que os resultados sejam reproduzidos corretamente, execute o notebook do início ao fim.

---


## Conclusão

A análise mostrou que o preço de venda dos imóveis é fortemente influenciado por variáveis relacionadas à qualidade geral da construção, área habitável, garagem, tamanho do porão, ano de construção e localização.

Na etapa supervisionada, a Regressão Linear apresentou bom desempenho na previsão dos preços, enquanto o Random Forest obteve o melhor resultado na classificação entre imóveis de preço alto e baixo.

Na etapa não supervisionada, o KMeans permitiu identificar grupos de imóveis semelhantes, o PCA auxiliou na visualização da estrutura dos dados e o LOF destacou possíveis imóveis atípicos.

Dessa forma, o projeto reúne as principais etapas de um fluxo de análise de dados e Machine Learning, passando pela exploração, preparação, modelagem, avaliação e interpretação dos resultados.

---

## Fonte dos dados

Dataset utilizado:

**House Prices: Advanced Regression Techniques — Kaggle**

