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


## Diferenças de Treinamento entre os Métodos de Ensemble
Regressão Ridge:

Emprega a técnica de regressão Ridge para realizar previsões.
Conduz uma pesquisa em grade para identificar o valor mais adequado para alpha, um parâmetro de regularização.
Vizinhos Mais Próximos (KNN):

Utiliza o regressor KNN para realizar previsões.
Executa uma pesquisa em grade para determinar o melhor valor para o número de vizinhos (n_neighbors).
Regressor de Árvore de Decisão:

Emprega uma árvore de decisão para realizar previsões.
Não incorpora etapas de pré-processamento específicas para este modelo.
SVR (Regressor de Vetores de Suporte) com Kernel RBF:

Utiliza um regressor de vetores de suporte com kernel RBF para realizar previsões.
Realiza uma pesquisa em grade para otimizar os parâmetros C (regularização) e epsilon.
Regressor de Floresta Aleatória:

Utiliza um regressor de floresta aleatória para realizar previsões.
Conduz uma pesquisa em grade para otimizar os hiperparâmetros da floresta aleatória.
Regressor AdaBoost:

Utiliza o regressor AdaBoost com uma árvore de decisão como base.
Não incorpora etapas de pré-processamento específicas para este modelo.
Regressor de Aumento de Gradiente:

Utiliza o regressor de aumento de gradiente para realizar previsões.
Não incorpora etapas de pré-processamento específicas para este modelo.
Voting Regressor:

Combina os resultados de modelos individuais (Gradient Boosting, AdaBoost, Ridge, SVR com Kernel RBF) por meio de votação.
Não incorpora etapas de pré-processamento específicas para este modelo.
Stacking Regressor:

Combina os resultados de modelos individuais (Gradient Boosting, AdaBoost, Ridge, SVR com Kernel RBF) usando um meta-regressor linear.
Não incorpora etapas de pré-processamento específicas para este modelo.
Regressor XGBoost:

Utiliza o regressor XGBoost para realizar previsões.
Conduz uma pesquisa em grade para identificar os melhores hiperparâmetros.
Modificações para Aprimorar o Modelo
Regressão Ridge:

Aplica um transformador de log nos alvos (y_log).
Realiza uma pesquisa em grade para identificar o melhor valor de alpha.
Vizinhos Mais Próximos (KNN):

Aplica um transformador de log nos alvos (y_log).
Realiza uma pesquisa em grade para identificar o melhor valor para o número de vizinhos (n_neighbors).
Regressor de Floresta Aleatória:

Aplica um transformador de log nos alvos (y_log).
Realiza uma pesquisa em grade para otimizar os hiperparâmetros da floresta aleatória.
SVR com Kernel RBF:

Aplica um transformador de log nos alvos (y_log).
Realiza uma pesquisa em grade para otimizar os parâmetros C e epsilon.
Regressor de Árvore de Decisão:

Aplica um transformador de log nos alvos (y_log).
Regressor AdaBoost:

Aplica um transformador de log nos alvos (y_log).
Regressor de Aumento de Gradiente:

Aplica um transformador de log nos alvos (y_log).
Voting Regressor:

Aplica um transformador de log nos alvos (y_log).
Stacking Regressor:

Aplica um transformador de log nos alvos (y_log).
Regressor XGBoost:

Aplica um transformador de log nos alvos (y_log).
Realiza uma pesquisa em grade para identificar os melhores hiperparâmetros.
Utiliza um conjunto de treinamento e validação para monitorar o desempenho durante o treinamento.
Essas adaptações têm como objetivo aprimorar o desempenho dos modelos, especialmente quando os alvos (variáveis dependentes) apresentam distribuição assimétrica. A utilização da transformação de log pode contribuir para estabilizar as variações e melhorar a interpretação dos resultados. A pesquisa em grade para otimização de hiperparâmetros é uma prática comum na busca das configurações que maximizem o desempenho do modelo.
