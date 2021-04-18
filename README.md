# Desafio-cognitivo-ai



## Previsão do preço da estadia (Airbnb / Rio de Janeiro-RJ)



### a. Como foi a definição da sua estratégia de modelagem?

A estratégia de modelagem teve início a partir de uma exploração e análise preliminar dos *datasets* fornecidos e dos dados presentes. Dentre os *datasets* fornecidos, foi selecionado o dataset 'listings.csv.gz' para a previsão do preço da estadia, por apresentar informações gerais sobre as acomodações (localização, número de quartos, número de banheiros, anfitrião, avaliações, etc) suficientes para uma predição do preço. Após a seleção do *dataset*, foi realizada uma limpeza inicial dos dados, removendo *features* sem dado algum, e também uma transformação de *features* importantes (número de banheiros e preço) em *features* numéricas. Em seguida foi feita uma avaliação a partir de uma análise de correlação e conhecimento do produto para seleção final das *features* a serem incluídas no *dataset* para modelagem.  

Inicialmente foi realizada uma modelagem por um modelo *baseline* (mais simples) para servir de parâmetro de comparação com outras modelagens mais complexas realizadas em seguida. O modelo baseline utilizado foi uma regressão múltipla. Para esta modelagem foi feita uma limpeza de linhas com dados ausentes (NaN), seleção de cinco *features*  e uma normalização das *features* utilizadas para predição do preço. O processo de normalização é importante pois a diferença de ordem de grandeza presente nas *features* prejudica a aplicação do modelo.



### b. Como foi definida a função de custo utilizada?

Foram utilizadas as mesmas funções de custo para os modelo testados: MAE (erro médio absoluto) e RMSE (raiz do erro quadrático médio), métricas geralmente utilizadas para avaliações de regressões. O modelo com menor erro médio absoluto foi o modelo de *Random Forest otimizado*. 

### c. Qual foi o critério utilizado na seleção do modelo final?

O critério usado na seleção do modelo final foi o que apresentou menores valores das métricas MAE e RMSE. Foram testados três modelos: regressão múltipla, *random forest* e *random forest otimizado*. O modelo *random forest otimizado* foi o que apresentou menores erros nas métricas utilizadas. Este modelo foi otimizado a partir de um modelo *random forest* onde foi feita uma seleção dos melhores hiperparâmetros.

### d. Qual foi o critério utilizado para validação do modelo?

Para validação do modelo foi feita uma separação da base de dados em treinamento e teste. A base utilizada para treinamento do modelo consistiu de 80% dos dados, os outros 20% foram usados para testar as predições.

### e. Quais evidências você possui de que seu modelo é suficientemente bom?

O modelo final apresentou, aproximadamente, MAE de 167 e RMSE de 417. É importante destacar que várias melhorias na análise podem ser realizadas para melhorar o predição da modelagem, como a separação das acomodações por zonas em vez de bairros, tratamento de dados faltantes etc.  



## Bônus: Análise de Keywords

Como análise adicional, foi feita uma avaliação das *keywords* presentes na *feature* '*comments*' do *dataset* 'reviews.csv.gz'. Tal *feature* contém avaliações feitas pelos hospedes sobre a estada nas acomodações. Utilizou-se o algoritmo '*tf-idf* ' para medir quais termos são de maior relevância nas avaliações correspondentes a cada acomodação. Como constam avaliações em diferentes línguas, foram selecionadas as duas línguas mais frequentes (inglês e português) para a análise. Observou-se diferenças nas *keywords* mais relevantes utilizadas por hospedes que escreveram em língua inglesa em relação aos que escreveram em português. Em inglês, as palavras mais utilizadas estão relacionadas ao anfitrião da acomodação e indicam uma preocupação com cancelamentos de reservas (*keywords*: *canceled*, *host*, *reservation*). Em português, as palavras indicam uma preocupação com maior com a localização e proximidade do metrô e conformo.

