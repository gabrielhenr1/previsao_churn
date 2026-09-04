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

## 📊 3. Modelos Avaliados e Métricas
Como o conjunto de dados de *churn* é desbalanceado, a **Acurácia foi descartada** como métrica principal para evitar falsas impressões. O foco analítico recaiu sobre a **Matriz de Confusão** e o **F1-Score da Classe 1 (Churn)**.

* **Regressão Logística (Baseline Linear):** Excelente capacidade de captura (*Recall* alto), porém com um volume elevado de Falsos Positivos (alarmes falsos para clientes que iriam ficar).
* **Random Forest (Espacial/Otimizado):** Escolhido como o melhor modelo corporativo. O ajuste de hiperparâmetros via Grid Search reduziu drasticamente os alarmes falsos, entregando o melhor equilíbrio entre Precisão e Sensibilidade (*F1-Score: 0.61*).
* **Gradient Boosting:** Apresentou forte tendência conservadora, limitando a taxa de detecção de cancelamentos reais.

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

## 🚀 6. Como Executar o Projeto
1. Clone o repositório:
   ```bash
   git clone [https://github.com/seu-usuario/seu-repositorio.git](https://github.com/seu-usuario/seu-repositorio.git)
