# ⚽ Premier League Goal Prediction - Machine Learning Project

Este projeto tem como objetivo prever a **quantidade de gols marcados em uma partida da Premier League**, utilizando algoritmos de **aprendizado de máquina supervisionado multiclasse**.

A tarefa consiste em classificar o número de gols em uma das seguintes categorias:

- `0 gols`
- `1 gol`
- `2 gols`
- `3 ou mais gols`

O modelo final pode ser usado em cenários reais de **análise esportiva**, **previsão de desempenho**, ou como base para **sistemas de recomendação e apostas esportivas inteligentes**.

---

## 📊 Pipeline do Projeto

### 1. 📥 Coleta e Pré-processamento dos Dados
- Leitura do dataset `all_seasons.csv` com estatísticas detalhadas da Premier League.
- Padronização de nomes de colunas, remoção de duplicatas e dados ausentes.
- Criação de variáveis relevantes (e.g. posse de bola, escanteios, finalizações).
- Criação da **variável alvo multiclasse** com as faixas de gols.

### 2. 🧼 Limpeza e Seleção de Variáveis
- Remoção de colunas não informativas ou correlacionadas.
- Transformação de dados categóricos com One-Hot Encoding.
- Normalização e escalonamento dos dados quando necessário.

### 3. 🔍 Análise Exploratória
- Distribuição das classes de gols.
- Correlação entre variáveis.
- Visualizações com Seaborn e Matplotlib.

### 4. 🎯 Seleção de Features com RFECV
- Uso de **RFECV (Recursive Feature Elimination with Cross-Validation)** com Random Forest.
- Identificação das features mais relevantes para o desempenho dos modelos.
- Redução da dimensionalidade para melhorar generalização.

### 5. ⚖️ Balanceamento de Classes
- Aplicação da técnica **SMOTE** (Synthetic Minority Oversampling Technique).
- Reamostragem das classes para evitar viés nos modelos.

### 6. 🤖 Modelagem Preditiva
Modelos testados:

| Modelo               | Tipo                        |
|----------------------|-----------------------------|
| Regressão Logística  | Linear, interpretável       |
| Random Forest        | Ensemble, robusto           |
| XGBoost              | Boosting, alta performance  |

Cada modelo foi avaliado com:

- **Validação cruzada estratificada (StratifiedKFold)**
- **Métricas multiclasse**:
  - F1-score macro
  - Acurácia
  - Matriz de confusão
  - **Curvas ROC por classe**

### 7. 🧠 Explicabilidade do Modelo
- Uso de **SHAP (SHapley Additive exPlanations)** para interpretação do modelo.
- Gráficos SHAP para identificar as variáveis mais impactantes nas decisões.

---

## 🏆 Melhor Modelo: Random Forest

O presente trabalho demonstrou que é viável prever faixas de gols em partidas da Premier League utilizando técnicas de aprendizado de máquina, a partir de dados estatísticos agregados.

> Entre os modelos avaliados, o **Random Forest** se destacou, atingindo desempenho superior em todas as métricas — com destaque para um **ROC-AUC de 0,98**, indicando excelente capacidade discriminativa entre as classes.

- O **XGBoost** também obteve resultados robustos, embora ligeiramente inferiores.
- A **Regressão Logística**, apesar de sua simplicidade e interpretabilidade, apresentou limitações na captura de padrões não lineares.

---

## 📈 Resultados

- **Modelo final salvo**: `Random Forest`
- **Desempenho**:
  - F1-score macro alto em todas as classes
  - ROC-AUC = **0.98**
- **Variáveis mais influentes**:
  - Finalizações
  - Posse de bola
  - Escanteios
  - Cartões e faltas

---
