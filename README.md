
### 2. Construir/Treinar

-   No SageMaker Canvas, importe o dataset que você selecionou.
-   Configure as variáveis de entrada e saída de acordo com os dados.
-   Inicie o treinamento do modelo. Isso pode levar algum tempo, dependendo do tamanho do dataset.

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



# Implementação da Previsão de Estoque Inteligente na AWS com SageMaker Canvas
Aqui está um exemplo de como foi implementado o desafio utilizando o dataset fornecido.

## 1. Selecionar Dataset
Utilizaremos o dataset dataset-1000-com-preco-variavel-e-renovacao-estoque.csv que contém as seguintes colunas:

- ID_PRODUTO: Identificador único do produto.
- DATA_EVENTO: Data do evento relacionado ao produto.
- PRECO: Preço do produto na data do evento.
- QUANTIDADE_ESTOQUE: Quantidade em estoque do produto na data do evento.
  
## 2. Construir/Treinar
- Importar Dataset: Foi feito o upload do dataset no SageMaker Canvas.
- Configurar Variáveis: Foi definido QUANTIDADE_ESTOQUE como a variável de saída (o que queremos prever) e as outras colunas como variáveis de entrada.
- Iniciar Treinamento: Configurado o modelo e inicie o treinamento.


## 3. Analisar
###Métricas de Performance: Após o treinamento, verifique as seguintes métricas de desempenho do modelo:

  - Avg. wQL (Average Weighted Quantile Loss): 1.027
    - Esta métrica avalia a precisão das previsões do modelo em diferentes quantis. Uma menor perda quantílica ponderada indica previsões mais precisas.
      
  - MAPE (Mean Absolute Percentage Error): 0.001
    - O MAPE mede a precisão das previsões como uma porcentagem. É a média dos erros absolutos dividida pelos valores reais, multiplicada por 100. Um valor mais baixo indica maior precisão.
      
  - WAPE (Weighted Absolute Percentage Error): 1.038
    - O WAPE é semelhante ao MAPE, mas leva em consideração o peso dos diferentes itens. Isso ajuda a entender a precisão das previsões considerando a importância relativa dos itens.
     
  - RMSE (Root Mean Squared Error): 2.085
    - O RMSE calcula a raiz quadrada da média dos erros quadrados. É uma métrica comum para medir a diferença entre os valores previstos pelo modelo e os valores observados. Um valor mais baixo indica melhores previsões.
    
  - MASE (Mean Absolute Scaled Error): 0.002
    - O MASE é a média dos erros absolutos escalados pelo erro médio de um modelo de referência. Uma pontuação de MASE menor que 1 indica que o modelo é melhor do que o modelo de referência.
