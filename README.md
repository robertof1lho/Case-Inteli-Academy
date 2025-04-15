# PS Inteli Academy - Roberto Filho

Este projeto tem como objetivo prever a rotatividade de clientes (churn) utilizando dados históricos da empresa fictícia TelecomPlus. A proposta é construir um modelo supervisionado de machine learning capaz de identificar clientes com maior risco de cancelamento, a fim de apoiar decisões estratégicas de retenção.

## Modelos Utilizados

Durante o desenvolvimento, foram testados diversos algoritmos de classificação, com e sem balanceamento de classes:

- Regressão Logística  
- K-Nearest Neighbors (KNN)  
- Decision Tree  
- Random Forest  
- XGBoost  
- LightGBM (com tuning via Optuna)

Além disso, foi implementado um **modelo híbrido em cascata**, combinando:

- Um modelo leve (Regressão Logística calibrada com validação cruzada)
- Um modelo robusto (XGBoost) aplicado apenas a casos ambíguos

Esse modelo híbrido obteve os melhores resultados gerais.

## Técnicas Aplicadas

- Análise exploratória dos dados (EDA)
- Tratamento de outliers e dados faltantes
- Engenharia de features (faixa etária, gastos, produtos assinados, etc.)
- Codificação ordinal de variáveis categóricas
- Balanceamento de classes via `class_weight` e `scale_pos_weight`
- Feature selection com `SelectKBest`
- Calibração de probabilidades com `CalibratedClassifierCV`
- Otimização de threshold de decisão com base em precisão mínima
- Validação cruzada estratificada (5-fold)

## Estrutura dos Arquivos

- `resolucao.ipynb`: Notebook com todas as etapas do projeto  
- `dados_clientes.csv`: Base de dados de treino  
- `desafio.csv`: Base de dados para predição final  
- `resultado_roberto_filho.csv`: Arquivo com a predição final sobre o `desafio.csv`  
- `requirements.txt`: Bibliotecas utilizadas no projeto  
- `README.md`: Este arquivo  

## Como Executar o Projeto

O projeto foi desenvolvido em Python utilizando ambiente virtual (`venv`). Abaixo estão os passos para execução:

### 1. Clonar o repositório

`git clone https://github.com/robertof1lho/Case-Inteli-Academy.git`

### 2. Criar e ativar o ambiente virtual

No Windows:

`python -m venv venv venv\Scripts\activate`

No Linux ou Mac:

`python3 -m venv venv source venv/bin/activate`

### 3. Instalar as dependências

`pip install -r requirements.txt`

### 4. Rodar o notebook

Abra o arquivo `resolucao.ipynb` com Jupyter Notebook ou diretamente pelo VSCode.

Se preferir abrir pelo terminal:

`jupyter notebook`
