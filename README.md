# Petroleum-derivatives-projection

Neste projeto, faço o uso de algoritmos estatísticos e de machine learning para a predição de derivados de petróleo (diesel e gasolina) na Áustria durante o ano de 2024.

Os dados utilizados vieram de fontes públicas ([JODI](https://www.jodidata.org/)), assumindo-se a premissa de que o dado é verídico.

Inicialmente houve o tratamento da base de dados com o objetivo de possibilitar a predição de forma acurada. Apesar do uso de conhecimentos prévios para a previsão de demanda, também é possível entender o impacto de cada uma das variáveis explicativas através do **feature importance** do modelo **XGBoost**.

Foram aplicados os modelos **XGBoost** e **Light GBM**, pois ambos utilizam árvores de decisão em seu método, o que pode ajudar a capturar comportamentos não lineares.

Apesar do problema, em sua essência, ser uma série temporal, ao comparar esses modelos com o **Prophet** — especializado em séries temporais — os modelos baseados em árvore se mostraram mais eficazes, apresentando um MAPE menor para ambos os casos.

O **Prophet** fez uso do método Bayesiano de Monte Carlo via Cadeia de Markov, com séries decompostas, o que traz uma flexibilidade maior para a adição de variáveis explicativas ao modelo de série temporal, diferentemente de modelos como **ARIMA** ou **SARIMA**, que também foram empregados ao longo do estudo.

## Resultados - MAPE dos Modelos

| Modelo           | MAPE Gasolina | MAPE Diesel |
|------------------|---------------|-------------|
| XGBoost          | 1,70%          | 3,19%       |
| Light GBM        | 2,17%          | 3,05%       |
| Prophet          | 61,75%         | 60,14%      |


## Execução do código

O código produzido foi implimentado no google colab, para uso, faça o download do código, baixe os dados no local descrito no início do código. Como foi realizado o uso do google colab, os dados estão em salvos em uma pasta dentro do google drive.

