# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Bem-vindo ao desafio de projeto "Previsão de Estoque Inteligente na AWS com SageMaker Canvas. Neste Lab DIO, eu mostrarei em prática os conhecimentos adquiridos sobre o SageMaker Canvas.

## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

Nesse README vou mostra passo a passo como fazer um treinamento de maquinha (ML), de forma low-code, usando as a ferramenta da AWS, SageMaker Canvas. Após isso mostrarei os resultados obtidos pelo ML, fazendo uma analise dos mesmos.


## 🚀 Passo a Passo

### 1. Selecionar Dataset

-  Primeiro vamos selecionar o nosso dataset, que no caso sera p dataset-1000-com-preco-promocional-e-renovacao-estoque, que esta disponivel na pasta de dataset do projeto, dento do SagaMaker canvas eu o chamei de "desafio_dio"
-  Importanto o dataset
  ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20225554.png?raw=true)
-  Nomeando o projeto
  ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20225639.png)


### 2. Construir/Treinar

-  Importanto o dataset para dentro do projeto
   ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20225704.png?raw=true)
-  Configurando a variavel que vamos analisar, no caso sera a QUANTIDADE_ESTOQUE, que mostra a quantidade de um produto no estoque eu uma data. Essa variavel sera responavel por modelar os nossos resultados que vão sair.
   ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20231422.png?raw=true)
-  Identificando qual sera o identificador unico (id) usado, que será o ID_PRODUTO. Após identificar ele, o aprendizado de maquina vai analisar o comportamento de cada id em relação a QUANTIDADE_ESTOQUE
   ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20231449.png?raw=true)
-  Após esses passos é so dar o quick build e eseperar finalizar o treinamento usando o dataset
   ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20231521.png?raw=true)

### 3. Analisar

  -  Agora vamos analisar as metricas que foram obtidas após o treinamento de dados 
   ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20230939.png?raw=true)

  - Avg.Wql (Average Weighted Quantile Loss)
    Avg.Wql (0.060) refere-se à média da perda quantílica ponderada. Essa métrica é útil quando queremos medir a precisão das previsões considerando diferentes quantis da distribuição dos dados. No contexto de        previsão de estoque, ela ajuda a entender como o modelo se comporta em diferentes níveis de demanda, ponderando as perdas para fornecer uma visão mais equilibrada do erro.
    
 - MAPE (Mean Absolute Percentage Error)
   MAPE (0.148) significa Erro Percentual Absoluto Médio. Esta métrica calcula a média dos erros absolutos em termos percentuais. É particularmente útil porque oferece uma compreensão intuitiva do erro em relação    ao valor real. Um MAPE de 0.021 indica que, em média, as previsões estão errando por cerca de 14.8%.

 - WAPE (Weighted Absolute Percentage Error)
   WAPE (0.10) representa o Erro Percentual Absoluto Ponderado. Esta métrica é similar ao MAPE, mas dá pesos diferentes aos erros com base em alguma característica (como a magnitude dos valores reais). Um WAPE      de 0.10 sugere que os erros absolutos médios ponderados são cerca de 10.0% dos valores reais, oferecendo uma medida robusta da precisão, especialmente útil em cenários com valores extremos.  

- RMSE (Root Mean Squared Error)
  RMSE (5.765) é o Erro Quadrático Médio. Ele calcula a raiz quadrada da média dos erros quadrados, penalizando mais severamente os erros maiores.Um RMSE de 5.765 indica que, em média, a magnitude do erro das 
  previsões é de aproximadamente 5.765 unidades. Essa métrica é sensível a outliers e oferece uma visão clara do desvio padrão das previsões em relação aos valores reais.

- MASE (Mean Absolute Scaled Error)
  MASE (0.301) refere-se ao Erro Absoluto Médio Escalonado. É uma métrica que compara o desempenho do modelo de previsão com um modelo de referência (geralmente um modelo de previsões ingênuas).Uma MASE  de 0.301   significa que o modelo de previsão está, em média, cometendo erros que são 30.1% do erro absoluto médio de um modelo de referência ingênuo. Vamos aprofundar um pouco mais no 
  significado e na interpretação dessa métrica.

- Além das metricas, outro fator importante que o ML mostrou é que a coluna PRECO influencia em 9.61% no resultado final da previsão. Ou seja o preço afeta diretamente a quantidade de itens que um produto terá no   estoque.

### 4. Prever

-   Agora vamos para a parte de preve. Nessa parte pegamos os produtos separados através do seu ID e analisamos os seus percentis (p10, p50, p,90).
   ![image](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20233554.png?raw=true)

-   Entendendo os Percentis: P10, P50 e P90
O que são percentis?
Os percentis são como marcadores que dividem um conjunto de dados ordenados em 100 partes iguais. Eles nos ajudam a entender onde um valor específico se encaixa dentro de um grupo de dados. Vamos explorar os percentis p10, p50, p90 de forma simples.

- Percentil 10
-P10 = 54.938

-Este valor indica que em 10% das vezes, a demanda por este produto será de 54.938 unidades ou menos. Isso representa um cenário de baixa demanda. É um valor útil para garantir que não teremos excesso de estoque quando a demanda for baixa.
-Exemplo prático: Imagine que você está planejando o estoque para o próximo mês. Se o P10 é 54.938, significa que em um cenário de baixa demanda, você precisará de pelo menos 54.938 unidades. Se p10 é 54.938, significa que é muito improvável que a demanda caia abaixo desse valor. Isso ajuda a planejar para um cenário de menor demanda, garantindo que você não fique com excesso de estoque.

- Percentil 50
-P50 = 62.181
-Este valor indica que em 50% das vezes, a demanda por este produto será de 62.181 unidades ou menos. Este é o valor médio esperado, ou seja, metade das vezes a demanda será menor que isso e metade das vezes será maior. É um bom ponto de partida para planejar o estoque.
-Exemplo prático: Se o P50 é 62.181, significa que em um mês típico, você precisará de cerca de 62.181 unidades para atender à demanda média.

- Percentil 90
-P90 = 71.467
-Planeje para ter até 71.467 unidades em estoque.Isso ajuda a garantir que você não fique sem estoque em períodos de alta demanda, como durante promoções ou picos sazonais.

-Resumindo
-Baixa demanda (P10): Se você planejar ter pelo menos 54.938 unidades, estará preparado para atender à demanda mínima esperada 90% das vezes.
-Demanda média (P50): Mantendo cerca de 62.181 unidades, você estará bem preparado para o cenário de demanda mais comum.
-Alta demanda (P90): Tendo até 71.467 unidades, você estará pronto para quase todos os cenários de alta demanda, garantindo que seus clientes não fiquem sem o produto.

