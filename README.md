#  Previsão de Demanda de Táxis por Hora – Taxi Corrida Maluca

##  Visão Geral

A empresa **Taxi Corrida Maluca** precisa prever a quantidade de pedidos de táxi na próxima hora para otimizar a disponibilidade de motoristas durante períodos de pico.

Este projeto utiliza técnicas de **Machine Learning para séries temporais** com o objetivo de construir um modelo preditivo com desempenho de **RMSE ≤ 48**.

---

##  Dados

- Fonte: `/datasets/taxi.csv`
- Variável alvo: `num_orders`
- Frequência original: dados sub-horários
- Frequência final: agregação por hora

---

## Etapas do Projeto

O projeto foi dividido em quatro etapas principais:

---

# Preparação dos Dados

Nesta etapa, os dados foram organizados e transformados para análise de série temporal.

### Processos realizados:
- Conversão da coluna de data para formato `datetime`
- Definição do índice temporal
- Ordenação cronológica dos dados
- Reamostragem para intervalos de 1 hora (soma dos pedidos)
- Verificação de valores ausentes

### Resultado:
Dados estruturados corretamente para modelagem temporal.

---

#  Análise Exploratória (EDA)

Foi realizada uma análise para identificar padrões e comportamento da série temporal.

### Principais achados:
- Presença de sazonalidade diária
- Picos de demanda em horários de rush
- Tendência e variação ao longo do tempo
- Comportamento não estacionário

### Técnicas usadas:
- Gráficos de série temporal
- Média móvel
- Decomposição de tendência e sazonalidade

---

#  Treinamento dos Modelos

Foram testados diferentes modelos de regressão com engenharia de features.

### Modelos utilizados:
- Linear Regression
- Random Forest
- LightGBM Regressor
- CatBoost Regressor

### Engenharia de Features:
- Lags (1, 2, 3 e 24 horas)
- Média móvel de 24 horas
- Variáveis temporais (hora, dia da semana)

### Validação:
- Divisão temporal dos dados
- 10% do dataset reservado para teste
- Sem embaralhamento (evita data leakage)

---

#  Teste e Avaliação

O modelo final foi avaliado no conjunto de teste.

### Métrica utilizada:
- **RMSE (Root Mean Squared Error)**

### Resultado final:
- O modelo atingiu **RMSE inferior a 48**, atendendo ao requisito do projeto.

---

##  Conclusão

O modelo desenvolvido conseguiu capturar padrões importantes da demanda de táxis, incluindo sazonalidade e tendências temporais.

### Principais aprendizados:
- Importância da reamostragem correta em séries temporais
- Impacto de features de defasagem (lags)
- Importância da validação temporal correta
- Comparação entre modelos tradicionais e modelos baseados em boosting

---

## Tecnologias Utilizadas

- Python
- Pandas
- NumPy
- Scikit-learn
- LightGBM
- CatBoost
- Matplotlib
- Seaborn
- Joblib

---

## Estrutura do Projeto
