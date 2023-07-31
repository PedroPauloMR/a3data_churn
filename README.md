# A3DATA - Case

# Sobre o Problema

- O objetivo deste teste é que você consiga explorar e demonstrar suas habilidades técnicas e de negócio, trazendo insights acionáveis para o negócio.
- Caso seja necessário, você pode definir premissas e suposições, basta justificá-las.

- Definição do problema:
    -   A empresa de telecomunicações contratou a A3Data para avaliar o cenário de churn elevado dos seus clientes e, uma vez que estamos falando de um produto com custo elevado de setup (instalação), a empresa gostaria de uma estratégia para reduzir esse churn.
    - Você pode desenvolver o teste em sua linguagem de programação de preferência.


# Sobre o dataset
- **customerID**: ID do cliente
- **gender**: gênero do cliente
- **SeniorCitizen**: se é um cidadão idoso (!?)
- **Partner**: se possui parceiro(a)
- **Dependents**: se possui dependentes
- **tenure**: meses de assinatura do serviço
- **PhoneService**: se possui ou não serviço de telefone
- **MultipleLines**:se possui ou não múltiplas linhas telefônicas
- **InternetService**:se possui ou não serviço de internet
- **OnlineSecurity**:se possui ou não segurança online
- **OnlineBackup**:se possui ou não backup online
- **DeviceProtection**:se possui ou não dispositivo de proteção
- **TechSupport**:se possui ou não suporte técnico
- **StreamingTV**:se possui ou não streaming na TV
- **StreamingMovies**:se possui ou não serviço de streamling com filmes
- **Contract**: tipo de contrato assinado
- **PaperlessBilling**: se a fatura é digital ou não (!?)
- **PaymentMethod**: método de pagamento
- **MonthlyCharges**: cobrança mensal
- **TotalCharges**: cobrança total
- **Churn**: se entrou em CHURN ou não


# Planejamento da solução

## Saída
- Entregar a acurácia da ferramenta;
- Apresentar os insights a partir das hipóteses levantadas;
- Propor alguma promoção que diminua o índice;

## Entrada
- 7.043 registros de clientes
- 21 features, sendo uma relacionada se o cliente entrou em churn ou não

## Tarefas
- Realizar a EDA, englobando: tratamento de outliers e dados faltantes, correlações, hipóteses
- Feature engineering para criar possíveis variáveis que auxiliem no modelo além de eliminar irrelevantes
- Criação do modelo preditivo para identificar os cliente em churn
- Levantar métricas de negócio que possam auxiliar na diminuição dessa taxa


# Hipóteses levantadas
### H1 - Clientes com MonthlyCharges maior ou igual a média apresentam maior churn que abaixo dela
### H2 - O gênero é irrelevante para o churn
### H3 - Clientes com PaperlessBilling = 0 apresentam maior churn que quem é 1
### H4 - Contrato do tipo Mês-a-Mês é o que apresenta maior índice de churn
### H5 - Quem possui DSL como serviço de internet possui maior índice de churn
### H6 - Quem não possui dependentes tem maior índice de churn
### H7 - Quem não tem parceiro tem maior índice de churn
### H8 - Tenure abaixo da média possui maior churn que acima dela
### H9 - Quem possui método de pagamento automático tem menor índice de churn de quem não optou por esse método
### H10 - Quem possui quantidade de serviços abaixo da média tem maior índice de churn de quem está acima dela


# Modelos Testados

- Logistic Regression
- Extra Trees
- Random Forest
- LightGBM
- KNN
- XGBoost


# Modelo escolhido

- Logistic Regression devido ao custo-benefício apresentado entre os dados balanceados e não balanceados
- Métricas finais (threshold = 0.63)
    - Precisão:  60,92 %
    - Recall:  61,14 %
- Insights: estão no código e na apresentação disponibilizada na pasta **apresentações**
- Cenários simulados:
    - Recuperação - cenário pessimista: R$  9955.47
    - Recuperação - cenário realista: R$  13273.96
    - ecuperação - cenário otimista: R$  14933.21
    - Média dos cenários: R$  13273.96
