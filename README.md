# Regressão Logística - Previsão de Cliques em Anúncios

Este projeto implementa um modelo de regressão logística para prever se um usuário clicará ou não em um anúncio baseado em características demográficas e comportamentais.

## 📋 Descrição

O projeto utiliza um conjunto de dados sintético de publicidade contendo informações sobre usuários e seus comportamentos de clique em anúncios. O objetivo é criar um modelo de machine learning capaz de prever a probabilidade de um usuário clicar em um anúncio.

## 🎯 Objetivo

Desenvolver um modelo de classificação binária para prever a variável `Clicked on Ad` (0 = não clicou, 1 = clicou) com base nas seguintes features:

- **Daily Time Spent on Site**: tempo médio gasto no site por dia
- **Age**: idade do usuário
- **Area Income**: renda média anual da área onde o usuário mora
- **Daily Internet Usage**: tempo médio gasto na internet por dia
- **Male**: 1 se o usuário for homem, 0 caso contrário

## 📊 Dataset

O conjunto de dados contém 1000 registros com as seguintes colunas:

- `Daily Time Spent on Site` (float64)
- `Age` (int64)
- `Area Income` (float64)
- `Daily Internet Usage` (float64)
- `Ad Topic Line` (str)
- `City` (str)
- `Male` (int64)
- `Country` (str)
- `Timestamp` (datetime64)
- `Clicked on Ad` (int64) - **variável alvo**

## 🚀 Como Executar

### Pré-requisitos

- Python >= 3.14
- pip ou uv (gerenciador de pacotes)

### Instalação das Dependências

#### Usando uv (recomendado):
```bash
uv sync
```

#### Usando pip:
```bash
pip install -r requirements.txt
```

### Executando o Notebook

1. Ative o ambiente virtual (se necessário)
2. Inicie o Jupyter Notebook:
```bash
jupyter notebook
```
3. Abra o arquivo `simple-logistic-reg.ipynb`
4. Execute as células sequencialmente

## 📁 Estrutura do Projeto

```
.
├── advertising.csv              # Conjunto de dados
├── simple-logistic-reg.ipynb    # Notebook com análise e modelo
├── pyproject.toml               # Configuração do projeto e dependências
├── requirements.txt             # Lista de dependências para pip
└── README.md                    # Este arquivo
```

## 🔍 Análise Realizada

O notebook realiza as seguintes etapas:

1. **Carregamento e Exploração dos Dados**
   - Leitura do arquivo CSV
   - Análise de tipos de dados e valores nulos
   - Conversão de Timestamp para datetime

2. **Análise Exploratória de Dados (EDA)**
   - Estatísticas descritivas
   - Visualização de distribuições (histogramas)
   - Análise de correlações entre variáveis
   - Pairplot colorido pela variável alvo

3. **Preparação dos Dados**
   - Seleção de features numéricas
   - Divisão treino/teste (70%/30%)

4. **Modelagem**
   - Treinamento de Regressão Logística
   - Previsões no conjunto de teste

5. **Avaliação do Modelo**
   - Classification Report (precision, recall, f1-score)
   - Matriz de Confusão
   - Análise de desempenho por classe

## 📈 Resultados

O modelo alcançou os seguintes resultados:

- **Acurácia geral**: 90%
- **Precision (classe 0)**: 85%
- **Precision (classe 1)**: 96%
- **Recall (classe 0)**: 96%
- **Recall (classe 1)**: 84%
- **F1-score (classe 0)**: 90%
- **F1-score (classe 1)**: 89%

O modelo apresenta bom desempenho geral, com ligeira vantagem na identificação de usuários que não clicam em anúncios.

## 🛠️ Tecnologias Utilizadas

- **pandas**: Manipulação e análise de dados
- **numpy**: Operações numéricas
- **matplotlib**: Visualização de dados
- **seaborn**: Visualização estatística avançada
- **scikit-learn**: Machine learning (divisão de dados, modelo e métricas)
- **jupyter**: Ambiente de notebook interativo

## 📝 Observações

- O modelo usa o solver `liblinear` para regressão logística
- `random_state=42` garante reprodutibilidade dos resultados
- Features categóricas (Ad Topic Line, City, Country) não foram utilizadas no modelo
- Timestamp foi convertido para datetime mas não foi utilizado como feature

## 👨‍💻 Autor

Projeto desenvolvido como parte de estudos de machine learning com regressão logística.

## 📄 Licença

Este projeto é para fins educacionais.
