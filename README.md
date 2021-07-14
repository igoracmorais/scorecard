# scorecard
Um exemplo de como construir uma analise de scorecard usando o python
Aqui é explicado como usar o pacote scorecardpy do Python (https://pypi.org/project/scorecardpy/) para fazer uma análise e construção de um modelo básico de scorecard. A motivação para esse post veio após um trabalho de mentoria em uma empresa de crédito no Brasil e a constatação da baixa disponibilidade de material em português sobre o tema. Para cumprir com esse objetivo, fiz uma divisão das explicações em 5 diferentes notebooks. O banco de dados utilizado é o tradicional adotado pelo próprio pacote para explicar as funções, e pode ser obtido, na sua forma pura, no link (https://www.kaggle.com/uciml/german-credit).

## 1. Dados_analise
   O banco de dados original usado nas ilustrações do pacote possui 1.000 linhas e 9 colunas, mas não contem a coluna de target, que representaria se a pessoa, em questão, entrou ou não em default. Nesse caso, disponibilizo um arquivo em csv "german_credit_data.csv" com uma simulação de dados para a coluna, cujo nome fica como "default". Usa-se o numpy para isso, considerando 30% dos clientes com default="yes". A seguir a descrição das variaveis usadas:  <br>
   <br>
Age: idade (numerico). <br>
Sex: sexo (string: male, female) <br>
Job: grau de instrução da pessoa (numerico: 0 - unskilled and non-resident, 1 - unskilled and resident, 2 - skilled, 3 - highly skilled) <br>
Housing: situacao residencial (string: own, rent, or free) <br>
Saving accounts: tamanho da conta bancaria (string - little, moderate, quite rich, rich) <br>
Checking account: quantidade de recurso na conta (numerico, in DM - Deutsch Mark) <br>
Credit amount: quantidade em credito (numerico, in DM) <br>
Duration: duracao em meses do credito (numerico, in month) <br>
Purpose: proposito do credito (string: car, furniture/equipment, radio/TV, domestic appliances, repairs, education, business, vacation/others <br>
default: (Variavel objetivo - yes: default; no: pagou) <br>
<br>
  Alem disso, há valores nulos em "saving accounts" e "checking account" e no notebook apresentamos algumas opções de como preencher esses valores. Os resultados são salvos e depois disponibilizados como "german_credi_data2.csv" para que se tenha uma reprodução igual nos notebooks seguintes. 
   
## 2. WOE_IV
   Nesse notebook explico os conceitos de WOE - Weight of Evidence e IV - Information Value que são aplicados posteriormente no estudo de scorecard. Esse processo é feito passo a passo, ou seja, as estatísticas são construídas "na mão". Isso dá um pouco de trabalho, mas entendo que seria a forma mais eficiente de se aprender o significado das mesmas e o cientista de dados que assim proceder adquire um conhecimento que irá diferencia-lo dos demais. Caso não queira ver como isso funciona no detalhe, pode pular esse notebook e ir direto para o notebook 3, onde mostro como aplicar o pacote scorecardpy, que tem essas fórmulas já prontas para apenas "apertar o botão".
   Os conceitos, comentários e demais observações sobre o WOE e IV são todos feitos diretamente no notebook.
   
## 3. Scorecardpy
   O pacote é idêntico ao que foi desenvolvido no R, com apenas algumas pequenas diferenças de opções de funções. A descrição do uso do pacote no Python é bem precária, com apenas um exemplo e mesmo assim pouco explicado. E em português, por exemplo, não encontraremos quase nada. Isso me motivou a desenvolver, de forma mais didática, esses notebooks e espero que sejam úteis. Sugiro ir no github do pacote e ver as fórmulas, isso irá proporcionar ao mesmo tempo uma melhor compreensão das mesmas e fortalecer o seu entendimento de como usar o Python. Para aqueles com facilidade em R, podem acessar o link (https://cran.r-project.org/web/packages/scorecard/index.html) e ver algumas explicações sobre as funções. O objetivo dessa primeira parte é criar os valores do woe e iv para cada uma das variaveis do arquivo "german_credit_data2.csv". Ao final salvamos os resultados em um novo arquivo de nome "woe_to_model.csv" para ser utilizado no notebook 4.

## 4. Modelo_basico


## 5. Inserindo_LR_no_scorecard
