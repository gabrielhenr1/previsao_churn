# 🏦 Previsão de Churn Bancário (Evasão de Clientes)

## 📌 1. Visão Geral do Projeto
O termo **Churn** refere-se à perda de clientes em um determinado serviço ou produto. No setor bancário, identificar antecipadamente os clientes com alta probabilidade de cancelamento de conta é vital para a retenção e saúde financeira da empresa. 
Este projeto desenvolve um modelo de Machine Learning preditivo para identificar esses clientes de forma preventiva, permitindo campanhas de retenção mais assertivas e eficientes.

---

## ⚙️ 2. Arquitetura e Fluxo do Projeto
O desenvolvimento seguiu as melhores práticas de Ciência de Dados para evitar vazamento de dados (*Data Leakage*) e garantir uma avaliação real:
1. **Análise Exploratória (EDA):** Investigação de distribuições, correlações e padrões demográficos/comportamentais (ex: impacto de gênero, país de residência e atividade do membro).
2. **Engenharia de Recursos (*Feature Engineering*):** Criação de variáveis sintéticas baseadas em regras de negócio (ex: razões entre saldo/salário e idade/tempo de cliente).
3. **Pré-processamento:** Divisão estrita dos dados (`train_test_split`) antes de aplicar o escalonamento (`StandardScaler`) e tratamento de desbalanceamento de classes.
4. **Modelagem e Baseline:** Comparação entre múltiplos algoritmos lineares e baseados em árvores.
5. **Otimização de Hiperparâmetros:** Uso do `GridSearchCV` para refinar o modelo vencedor.

---

## 📊 3. Desempenho do Modelo

Por se tratar de um projeto direto ao ponto, o foco principal foi lidar com dados desbalanceados. Por isso, a Acurácia global foi deixada em segundo plano e a avaliação foi centrada no **F1-Score da Classe 1 (Churn)**.

O modelo vencedor, após a otimização de hiperparâmetros, foi o **Random Forest**, que apresentou a seguinte qualidade no conjunto de teste:

* **F1-Score (Churn):** 0.61
* **Recall (Sensibilidade):** 62% (Identificou 310 clientes que dariam churn)
* **Precisão:** 60% (Reduziu os falsos positivos para apenas 205 alarmes falsos)
* **Acurácia Global:** 85%

Esses números mostram um modelo equilibrado e funcional, capaz de encontrar a maioria dos cancelamentos sem onerar a empresa disparando falsos alertas para a grande base de clientes retidos.

---

## 🛠️ 4. Tecnologias e Bibliotecas Utilizadas
* **Linguagem:** Python 
* **Manipulação e Análise:** Pandas, NumPy
* **Visualização:** Matplotlib, Seaborn, Plotly
* **Machine Learning:** Scikit-Learn (LogisticRegression, RandomForestClassifier, GradientBoostingClassifier, GridSearchCV, métricas de avaliação)

---

## 🔍 5. Principais Insights de Negócio
- **Membros Inativos:** Clientes classificados como inativos apresentam uma propensão estatisticamente muito maior ao *churn*.
- **Localização:** A filial da Alemanha destacou-se com taxas proporcionais de cancelamento superiores em comparação a França e Espanha, apesar do volume total de clientes ser menor.
- **Redução de Custos Operacionais:** O modelo otimizado protege o orçamento do banco, evitando o desperdício de incentivos financeiros em Falsos Positivos.

---
