# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Bem-vindo ao desafio de projeto "Previsão de Estoque Inteligente na AWS com SageMaker Canvas. Neste Lab DIO, eu mostrarei em prática os conhecimentos adquiridos sobre o SageMaker Canvas.

## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

Nesse README vou mostra passo a passo como fazer um treinamento de maquinha (ML), de forma low-code, usando as a ferramenta da AWS, SageMaker Canvas. Após isso mostrarei os resultados obtidos pelo ML, fazendo uma analise dos mesmos.


## 🚀 Passo a Passo

### 1. Selecionar Dataset

-  Primeiro vamos selecionar o nosso dataset, que no caso sera p dataset-1000-com-preco-promocional-e-renovacao-estoque, que esta disponivel na pasta de dataset do projeto, dento do SagaMaker canvas eu o chamei de "desafio_dio"
-  Importanto o dataset
  ![image]([https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650](https://github.com/Caio-Henriquee/lab-aws-sagemaker-canvas-estoque/blob/main/img/Captura%20de%20tela%202024-06-27%20225554.png?raw=true))
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

-   Após o treinamento, examine as métricas de performance do modelo.
-   Verifique as principais características que influenciam as previsões.
-   Faça ajustes no modelo se necessário e re-treine até obter um desempenho satisfatório.

### 4. Prever

-   Use o modelo treinado para fazer previsões de estoque.
-   Exporte os resultados e analise as previsões geradas.
-   Documente suas conclusões e qualquer insight obtido a partir das previsões.

## 🤔 Dúvidas?

Esperamos que esta experiência tenha sido enriquecedora e que você tenha aprendido mais sobre Machine Learning aplicado a problemas reais. Se tiver alguma dúvida, não hesite em abrir uma issue neste repositório ou entrar em contato com a equipe da DIO.
