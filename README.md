# Clinical Analysis Laboratory

Projeto de Machine Learning desenvolvido em Python utilizando **Pandas**, **Matplotlib**, **Seaborn** e **Scikit-learn** para análise de um conjunto de dados de exames clínicos e construção de modelos de regressão linear.

## Objetivo

O projeto realiza uma análise exploratória dos dados de pacientes e desenvolve modelos de Machine Learning capazes de prever o resultado de exames clínicos a partir de características físicas e clínicas dos pacientes.

Além disso, o projeto compara o desempenho de dois modelos de regressão linear, avaliando a influência do Índice de Massa Corporal (IMC) na predição.

---

## Tecnologias utilizadas

- Python
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

---

## Estrutura do projeto

```
Clinical_analysis_laboratory/
│
├── datasets/
│   └── exames_diabete.csv
├── modelo_diabete.ipynb
├── requirements.txt
└── README.md
```

---

## Etapas do projeto

### 1. Carregamento dos dados

O conjunto de dados é importado utilizando o Pandas.

```python
pd.read_csv('./datasets/exames_diabete.csv')
```

---

### 2. Pré-processamento

São realizadas algumas etapas de preparação dos dados:

- remoção da coluna `id_paciente`;
- transformação da variável categórica `genero` em variável numérica utilizando **One-Hot Encoding**;
- criação de uma nova feature denominada **IMC**.

O IMC é calculado pela fórmula:

```
IMC = peso / altura²
```

---

### 3. Análise Exploratória dos Dados (EDA)

São geradas diversas visualizações para compreender melhor o comportamento das variáveis.

Entre elas:

- mapa de calor da correlação entre todas as variáveis;
- mapa de calor da correlação com a variável alvo (`resultado`);
- matriz de dispersão (*Scatter Matrix*);
- histogramas de todas as variáveis.

Essas análises ajudam a identificar relações entre os atributos e possíveis padrões existentes no conjunto de dados.

---

## Machine Learning

O projeto utiliza **Regressão Linear** para prever a variável alvo (`resultado`).

Os dados são divididos em:

- 70% para treinamento;
- 30% para teste.

A divisão é realizada utilizando:

```python
train_test_split()
```

---

## Modelo 1

O primeiro modelo utiliza praticamente todas as variáveis do conjunto de dados, exceto:

- resultado (target);
- IMC.

Features utilizadas:

- idade;
- altura;
- peso;
- pressão arterial;
- glicose;
- gênero.

---

## Modelo 2

O segundo modelo utiliza apenas uma variável independente:

- IMC.

Este modelo busca verificar o quanto o Índice de Massa Corporal é capaz de explicar sozinho o resultado dos exames.

Ao final, também é gerado um gráfico contendo:

- pontos reais do conjunto de teste;
- reta de regressão calculada pelo modelo.

---

## Avaliação dos modelos

Os modelos são avaliados utilizando duas métricas principais.

### R² (Coeficiente de Determinação)

Indica o quanto as variáveis de entrada conseguem explicar a variável alvo.

Valores próximos de **1** representam melhor desempenho.

---

### MAE (Mean Absolute Error)

Representa o erro absoluto médio entre os valores previstos e os valores reais.

Quanto menor o MAE, melhor é o desempenho do modelo.

---

## Bibliotecas utilizadas

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_absolute_error, r2_score
```

---

## Objetivo educacional

Este projeto tem como finalidade demonstrar um fluxo completo de um problema de Machine Learning utilizando regressão linear, passando pelas etapas de:

- importação dos dados;
- pré-processamento;
- engenharia de atributos (Feature Engineering);
- análise exploratória;
- treinamento do modelo;
- geração de predições;
- avaliação de desempenho.

---

## Autor

**João Victor Nascimento Ribeiro**