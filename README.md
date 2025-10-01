Bibliotecas: Usa pandas para manipulação de dados, scikit-learn para o ML, e numpy para simulação.

Simulação de Dados: Cria um dataset de 500 alunos com as três features de baixo volume (FET, DAP, TF). A variável Abandono (Target) é rotulada com alta probabilidade de ser 1 (abandono) se as features de risco (baixo engajamento/nota e altas faltas) forem atendidas.

Random Forest (RandomForestClassifier):

Utiliza o parâmetro class_weight='balanced_subsample' para instruir o algoritmo a dar mais peso aos casos raros de abandono, o que é crucial para maximizar o Recall (encontrar todos os casos positivos).

Avaliação: As métricas (Acurácia, Precisão e Recall) são calculadas. Os valores simulados no código geralmente produzem um Recall alto, confirmando o resultado chave do seu artigo.

Predição e Score de Risco:

predict_proba é usado para obter a probabilidade de um aluno pertencer à classe 1 (Abandono). Esta probabilidade é o Score de Risco (S 
R
​
 ).

Um Limiar de Risco (neste caso, 70%) é aplicado para classificar o aluno como Alto Risco.

Alerta Low-Bandwidth: O código simula a geração de uma mensagem SMS/USSD simples (apenas texto) contendo o ID do aluno, o Score de Risco e as features críticas (TF, DAP), garantindo o baixo volume de dados e a intervenção imediata.
