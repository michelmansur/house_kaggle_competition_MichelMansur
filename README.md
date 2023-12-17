# House Prices - Advanced Regression Techniques

Olá! Se você está aqui, quer dizer que passamos da Sprint 3, maravilha! Agora vamos focar em descobrir padrões dos nossos dados, e esta atividade ponderada é perfeita para consolidarmos o nosso conhecimento. Em grupo, se juntem e entrem no site: [house_kaggle_competition](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques), leiam o desafio, baixem os dados, façam uma pequena análise e criem seus notebooks para solucionar o problema proposto. Boa sorte! Não esqueça de submeter o desafio global, vamos tentar chegar nos 100 primeiros do mundo!

## Para que eu possa corrigir a sua ponderada, faça o `git clone` deste repositório, faça suas modificações (lembre-se que este notebook ajudará você e seu grupo à desenvolver o relatório do Artefato, em relação à ocrrelações dos dados), crie uma branch com seu nome, e faça um commit das suas modificações NA SUA BRANCH. No card coloque o link do seu commit =)

## Claro, o Barema da ponderada segue:

Desenvolvimento e Submissão de Soluções para o Desafio House Kaggle

1. Compreensão do desafio House Kaggle, incluindo o contexto e os objetivos do desafio;
2. Implementação das soluções do desafio no notebook preparatório de forma que passem nos testes pré-setados;
3. Utilização de técnicas, algoritmos e bibliotecas para a resolução dos problemas propostos;
4. Submissão das soluções desenvolvidas ao Kaggle Open Challenge;
5. Descrição dos requisitos para o desenvolvimento das soluções e compreensão do desafio House Kaggle;
6. Explicação detalhada do desenvolvimento das soluções, avaliação, otimização e submissão ao Kaggle utilizando comentários no código;

A escrita do texto deve ser clara, precisa e livre de erros ortográficos. Será descontado até 20% dos pontos caso sejam encontrados erros de ortografia.

Avançado (9,1 - 10): cumpriu todos os 6 itens descritos acima;

Intermediário (7,1 - 9): cumpriu 5 dos 6 itens descritos acima;

Básico (4,1 - 7): cumpriu 4 dos 6 itens descritos acima;

Insuficiente (0 - 4): cumpriu menos que 3 itens descritos acima.

## PONDERADA
Descreva aqui as diferenças de treinamento que você encontrou entre os treinamentos de Ensemble. Passe por todos os métodos. Descreva as modificações que você porpôs.

## Compreensão do desafio House Kaggle
A proposta do desafio visa antecipar o custo de residências considerando elementos como atributos físicos, estado do imóvel, local, entre muito outros.

## Implementação das soluções e utilização de técnicas, algoritmos e bibliotecas:

O script do desafio demonstra a aplicação de métodos de Machine Learning para antecipar os valores de propriedades, desde a formatação dos dados, empregando as bibliotecas Pandas e NumPy, até a utilização de algoritmos como Ridge, KNN, SVM, Árvores de Decisão, e assim por diante.


## Descrição dos Modelos:
Agora, segue uma descrição de todos os modelos, incluindo uma comparação.
## Ridge utilizando log-target:
Implementa um modelo Ridge para a tarefa de regressão.
Emprega um pipeline que envolve etapas de pré-processamento (preproc), o modelo Ridge e caching em memória.
Executa validação cruzada com 5 partições utilizando a métrica rmse (raiz do erro quadrático médio).
## KNN com Busca em Grade:
Utiliza o algoritmo K-Nearest Neighbors para regressão.
Adota um pipeline semelhante ao anterior, incorporando etapas de pré-processamento (preproc), o modelo KNN e caching em memória.
Realiza uma pesquisa em grade para ajuste dos hiperparâmetros (n_neighbors) por meio de validação cruzada com 3 partições e a métrica rmse.
## Random Forest com SelectFromModel:
Implementa um modelo Random Forest para tarefa de regressão.
Aplica um pipeline que inclui etapas de pré-processamento (preproc), o modelo Random Forest e a seleção de características através do SelectFromModel usando um estimador RandomForestRegressor.
Efetua validação cruzada com 5 partições utilizando a métrica rmse.
## SVR com Busca em Grade:
Utiliza o Support Vector Regressor para regressão.
Utiliza um pipeline com pré-processamento (preproc) e o modelo SVR. Realiza uma pesquisa em grade para otimização dos hiperparâmetros (C e epsilon) através de validação cruzada com 5 partições e a métrica rmse.
## Decision Tree:
Utiliza uma árvore de decisão para a tarefa de regressão.
Emprega um pipeline que engloba etapas de pré-processamento (preproc) e o modelo DecisionTreeRegressor.
Conduz validação cruzada com 5 partições utilizando a métrica rmse.
## Ensemble (VotingRegressor):
Combina diversos modelos (Gradient Boosting, AdaBoost, Ridge, SVM) usando o VotingRegressor.
Emprega um pipeline com pré-processamento (preproc) e o modelo de conjunto.
Realiza validação cruzada com 5 partições utilizando a métrica rmse.
## Ensemble (StackingRegressor):
Utiliza um modelo de empilhamento que acumula os resultados de diferentes modelos (Gradient Boosting, AdaBoost, Ridge, SVM) usando um modelo final de Regressão Linear.
Adota um pipeline com pré-processamento (preproc) e o modelo de empilhamento.
Efetua validação cruzada com 5 partições utilizando a métrica rmse.
## XGBoost com Validação Cruzada:
Implementa o XGBoost para regressão.
Emprega um pipeline com pré-processamento (preproc) e o modelo XGBoost.
Conduz validação cruzada com 5 partições utilizando a métrica rmse.
## XGBoost com Early Stopping:
Utiliza o XGBoost com early stopping para prevenir overfitting.
Realiza treinamento em dois conjuntos (treino e validação) e exibe o gráfico da métrica rmse durante o treinamento.
Emprega um pipeline com pré-processamento (preproc) e o modelo XGBoost.


## Sugestões para Aprimoramento:
Agora, segue as sugestões de aprimoramento de codigo do desafio.
Aprimoramento dos Hiperparâmetros:
Em relação a cada modelo, é recomendável realizar uma busca mais abrangente de hiperparâmetros, visando otimizar o desempenho.
Engenharia de Características:
Investigue a criação de novas características que possam elevar a capacidade preditiva do modelo.
Análise de Resíduos:
Conduza uma análise detalhada dos resíduos para compreender melhor as áreas em que os modelos estão apresentando deficiências e ajuste conforme necessário.
Ajuste de Pesos no Conjunto:
Experimente ajustar as ponderações dos modelos no conjunto para otimizar o desempenho geral.
Partições na Validação Cruzada:
Considere aumentar o número de partições na validação cruzada para avaliar a estabilidade do desempenho do modelo.
Avaliação de Modelos Individualmente:
Analise o desempenho de cada modelo individualmente para compreender suas contribuições para o conjunto.
Identificação e Tratamento de Pontos Atípicos:
Considere detectar e tratar valores discrepantes nos dados, pois esses podem ter um impacto negativo no desempenho do modelo.
Experimentação com Outros Modelos:
Explore algoritmos de regressão adicionais para avaliar se diferentes abordagens podem otimizar o desempenho.
Lembre-se de ajustar essas sugestões de acordo com a natureza específica do problema e dos dados em questão.
Essas modificações visam aprimorar o desempenho dos modelos, especialmente quando os alvos (variáveis dependentes) apresentam uma distribuição assimétrica. A aplicação da transformação logarítmica pode contribuir para estabilizar as variações e melhorar a interpretação dos resultados. A busca em grade para otimização de hiperparâmetros é uma prática comum na busca das configurações que maximizem o desempenho do modelo.
