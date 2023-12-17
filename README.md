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


## Descrição dos Modelos de regressã0:
Agora, segue uma descrição de todos os modelos de regressão.
## Ridge Regression
A abordagem de regressão Ridge representa um procedimento de regularização que introduz um termo de penalização na função de perda, visando mitigar a multicolinearidade em conjuntos de dados que englobam várias variáveis. Para identificar a solução mais adequada, o parâmetro de regularização, designado como Gama, passou por otimização por meio do método GridSearchCV, resultando em um valor otimizado de 2,0.

## K-Nearest Neighbors (KNN):
Descrição: O algoritmo KNN representa uma técnica de aprendizado supervisionado, efetuando previsões ao calcular a média dos rótulos pertencentes aos k vizinhos mais próximos no espaço de características. Estratégias de Ajuste: Otimização do parâmetro de quantidade de vizinhos (n_neighbors) realizada por meio do método GridSearchCV, com o valor final ajustado para 6. Máquina de Vetores de Suporte - Base Radial

## Function (SVM-RBF):
Descrição: A SVM com função de base radial (SVM-RBF) é um modelo de máquina de vetores de suporte que utiliza uma função de núcleo radial. Estratégias de Ajuste: Realizou-se a otimização dos parâmetros C e epsilon por meio do GridSearchCV, resultando nos valores ajustados de C=1 e epsilon=0.05.

## Random Forest:
Descrição: Uma floresta aleatório constitui-se de um conjunto de árvores de escolhas treinadas em amostragens aleatórias extraídas dos dados. Estratégias de Ajuste: Limitação da profundidade máxima para 50 e estabelecimento do número mínimo de amostras em folhas em 20.


## Decision Tree:
Descrição: Um método de árvore de escolhas separa os dados em seções conforme as características presentes nos dados. Estratégias de Ajuste: Limitação da profundidade máxima para 50 e estabelecimento do número mínimo de amostras em folhas em 20.




## Descrição dos Modelos de Ensemble:
Agora, segue uma descrição de todos os modelos de Ensemble.

## AdaBoost Regressor:
Descrição: O AdaBoost é uma técnica de impulsionamento que agrega múltiplos modelos de aprendizado de baixa complexidade. Estratégias de Ajuste: Utilização de Árvore de Escolhas como modelo base.

## Gradient Boosting Regressor:
Descrição: O Gradient Boosting desenvolve árvores de escolhas de maneira sequencial, retificando as imprecisões dos modelos prévios. Estratégias de Ajuste: Configuração de 100 estimadores.

## Voting Regressor:
Descrição: O Regressor de Votação agrega as predições de diversos modelos de regressão. Estratégias de Ajuste: Conjunto de Gradient Boosting, AdaBoost, Ridge e SVM com função de base radial.

## Stacking Regressor:
Descrição: O Regressor de Empilhamento combina vários modelos de regressão. Estratégias de Ajuste: Conjunto com características análogas ao Regressor de Votação.

## XGBoost (Extreme Gradient Boosting):

Descrição: O XGBoost representa um algoritmo de impulsionamento de gradiente eficaz e dimensionável. Estratégias de Ajuste: Profundidade máxima estabelecida em 10, número de estimadores definido como 300, e taxa de aprendizado ajustada para 0.1.

## Comparação dos resultados dos modelos.

A métrica de avaliação utilizada foi o RMSE, e a análise foi realizada considerando a média e o desvio padrão dos resultados durante a validação cruzada. Modelos mais elaborados, como o Gradient Boosting, Voting Regressor e Stacking Regressor, demonstraram RMSE mais reduzido. O XGBoost também exibiu um desempenho consistente. Abordagens como Ridge, KNN e SVM com função de base radial apresentaram resultados competitivos. A seleção do modelo final dependerá de vários fatores, incluindo as características dos dados, a interpretabilidade e os recursos computacionais disponíveis. O ajuste de hiperparâmetros desempenha um papel essencial na otimização do desempenho.



## Sugestões para Aprimoramento:
Agora, segue as sugestões de aprimoramento de codigo do desafio.


1. Feature Engineering - Explorar técnicas avançadas de engenharia de características para criar novos atributos relevantes para o problema
2. Ajuste de Hiperparametros Adicional - Realizar ajuste de hiperparâmetros mais detalhado
3. Tratamento de Outliers -Investigar a presença de outliers nos dados e considerar estratégias para tratá-los.
4. Avaliação de sensibilidade -  Realizar análises de sensibilidade para entender a influência de diferentes hiperparâmetros na performance do modelo.
   
