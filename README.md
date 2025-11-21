# 📈 Previsão de Preços de Ações (Machine Learning - Regressão)

## 💡 Visão Geral do Projeto

Este projeto foca na **Regressão de Séries Temporais** de curto prazo, utilizando o Machine Learning clássico para prever o preço de fechamento de uma ação (TICK3) com base em dados do dia anterior.

O objetivo é demonstrar a capacidade de construir um modelo de **Regressão** com alta **explicabilidade**, essencial para a tomada de decisão no mercado financeiro.

---

## 🚀 Tecnologias e Metodologia

| Fase | Descrição | Foco | Ferramentas Chave |
| :--- | :--- | :--- | :--- |
| **Data Prep** | Estruturação de dados no formato de Série Temporal (dados de um dia para prever o próximo). | Séries Temporais | `Pandas` |
| **Algoritmo** | **Regressão Linear** | Interpretabilidade e Modelagem Rápida | `sklearn.linear_model.LinearRegression` |
| **Avaliação** | **Erro Quadrático Médio (MSE)** e **R-Quadrado ($\text{R}^2$)** | Precisão e Ajuste | `sklearn.metrics` |
| **Explicabilidade (XAI)** | Análise dos coeficientes para desmembrar a previsão. | Transparência | Coeficientes do Modelo |

---

## ✅ Resultados e Análise de Desempenho

O modelo foi treinado com **Fechamento Anterior**, **Volume** e **Noticia Positiva** como variáveis de entrada.

### 1. Métricas de Avaliação

O modelo demonstrou um ajuste excepcional aos dados de treino:

* **R-Quadrado ($\text{R}^2$):** **0.9680** (96.8% da variação do preço é explicada pelo modelo).
* **Erro Quadrático Médio (MSE):** **0.0047** (RMSE: $\approx$ R\$ 0,07 de erro médio).

### 2. Interpretabilidade: Peso dos Fatores

A análise dos coeficientes revela os motores da previsão:

| Fator | Coeficiente | Interpretação (Peso) |
| :--- | :--- | :--- |
| **Fechamento Anterior** | **+1.1830** | Fator dominante. O preço de hoje é impulsionado pelo preço de ontem (Inércia). |
| **Notícia Positiva** | +0.3536 | Forte impacto positivo (R\$ 0,35 de aumento imediato). |
| **Volume** | -0.0039 | Impacto quase nulo ou marginalmente negativo. |

### 3. Explicabilidade (XAI): Desmembramento da Previsão (Dia 15/05)

A previsão de **R\$ 10,95** é totalmente rastreável, demonstrando a transparência do modelo:

| Fator | Contribuição no Preço |
| :--- | :--- |
| Fechamento Anterior | +R\$ 13.07 |
| Volume | -R\$ 0.89 |
| Intercepto (Base) | -R\$ 1.23 |
| **Preço Previsto** | **R$ 10.95** |

> **Conclusão de Mercado:** O modelo prevê alta (R\$ 10,95 vs. R\$ 11,05 do dia anterior), impulsionada quase inteiramente pela inércia do fechamento anterior.
