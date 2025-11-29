# Previsão de Preços de Criptomoeda 💰📈

## 📋 Visão Geral

Este projeto aplica técnicas de **Machine Learning** e **Análise de Séries Temporais** para prever o preço do Bitcoin (BTC-USD) em curto prazo. Desenvolvido como projeto final da disciplina de "Mineração de Dados e Aprendizado de Máquina" do curso de Ciência da Computação, o trabalho compara o desempenho de três modelos distintos de previsão.

### 👥 Equipe
- Gabriel Passos de Oliveira
- Letícia Yuri Hiratsuka

## 🎯 Objetivo

O problema central é realizar **previsões precisas do preço do Bitcoin** utilizando dados históricos de mercado. Para isso, implementamos e comparamos três abordagens diferentes:

1. **Regressão Linear** - Modelo estatístico clássico
2. **ARIMA** - Modelo especializado em séries temporais
3. **LSTM** (Long Short-Term Memory) - Rede neural recorrente com memória

## 📊 Dataset

Os dados foram coletados através da biblioteca `yfinance`, abrangendo o período de **2017 a 2024**. As principais features utilizadas incluem:

- **Close**: Preço de fechamento (variável alvo)
- **Open**: Preço de abertura
- **High**: Preço máximo do dia
- **Low**: Preço mínimo do dia
- **Volume**: Volume de negociação
- **SMA_20**: Média Móvel Simples de 20 dias
- **EMA_10**: Média Móvel Exponencial de 10 dias
- **Pct_Change**: Variação percentual diária

## 🔧 Tecnologias e Bibliotecas

- **Python 3.x**
- **TensorFlow/Keras** - Para implementação da rede LSTM
- **Scikit-learn** - Pré-processamento e modelos tradicionais
- **Statsmodels** - Modelo ARIMA
- **yfinance** - Coleta de dados financeiros
- **Pandas & NumPy** - Manipulação de dados
- **Matplotlib & Seaborn** - Visualização

## 🚀 Metodologia

### 1. Coleta e Análise Exploratória
- Download de dados históricos do Bitcoin
- Análise de correlação entre features
- Visualização de tendências e padrões

### 2. Pré-processamento
- Criação de indicadores técnicos (SMA, EMA)
- Normalização com MinMaxScaler
- Divisão em 80% treino e 20% teste
- Criação de janelas temporais (60 timesteps) para LSTM

### 3. Otimização de Hiperparâmetros
- Validação temporal (20% do treino separado para validação)
- Grid search manual testando:
  - Units: [50, 100]
  - Batch size: [1, 16, 32]
  - Epochs: [20, 40]

### 4. Treinamento
- Regressão Linear com features achatadas
- ARIMA com ordem (5, 1, 0)
- LSTM otimizado com melhores hiperparâmetros

### 5. Avaliação
Métricas utilizadas:
- **MAE** (Mean Absolute Error)
- **RMSE** (Root Mean Squared Error)
- **MAPE** (Mean Absolute Percentage Error)

## 📈 Resultados

O projeto demonstra a comparação entre modelos clássicos e modernos para previsão de séries temporais financeiras, avaliando qual abordagem oferece melhor performance para prever o preço do Bitcoin.

## 💻 Como Executar

### No Google Colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/GPassos01/md_ml/blob/main/ProjetoML.ipynb)

### Localmente
```bash
# Instalar dependências
pip install yfinance pandas numpy matplotlib seaborn scikit-learn statsmodels tensorflow

# Executar o notebook
jupyter notebook ProjetoML.ipynb
```

## 📁 Estrutura do Projeto

```
machine-learning/
├── ProjetoML.ipynb    # Notebook principal com toda a implementação
└── README.md          # Este arquivo
```

## 📝 Observações

- O modelo LSTM utiliza janelas temporais de 60 dias para fazer previsões
- Os dados são normalizados para melhorar a convergência dos modelos
- A validação temporal é crucial para evitar data leakage em séries temporais
- O projeto foi desenvolvido no Google Colab para aproveitar recursos de GPU
