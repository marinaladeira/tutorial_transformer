# Transformer para Tradução

Repositório baseado no tutorial oficial do TensorFlow: https://www.tensorflow.org/text/tutorials/transformer?hl=pt-br  
O código implementa um modelo Transformer para tradução de frases do português para inglês.

## Tutorial
- Utilização do dataset `ted_hrlr_translate/pt_to_en` para tradução.  
- Preparação e tokenização dos dados, com criação de lotes de treino e validação.  
- Implementação das principais camadas do Transformer: *Positional Encoding*, *Multi-Head Attention*, *Encoder* e *Decoder*.  
- Compilação do modelo com otimizador Adam, função de perda *SparseCategoricalCrossentropy* e métrica de acurácia.  
- Treinamento em diferentes ambientes (CPU e GPU) para comparação de desempenho.  
- Tradução de frases em português como etapa final de inferência.

## Avaliação do Treinamento em CPU e GPU
O treinamento foi realizado na CPU e GPU, como forma de teste do tempo de execução e capacidade.  

- **Execução em CPU**: o tempo de treinamento por época foi significativamente elevado, tornando inviável realizar um número maior de épocas. Essa limitação impacta diretamente na capacidade de avaliar melhorias graduais no modelo. O uso exclusivo de CPU restringe a experimentação prática a poucas execuções de teste.  

- **Execução em GPU**: o tempo por época foi drasticamente reduzido, permitindo treinar o modelo por mais épocas em um intervalo de tempo razoável. A utilização da GPU viabilizou acompanhar a convergência do modelo, observar ganhos na métrica de acurácia e gerar resultados de tradução mais consistentes.  

Para modelos de arquitetura Transformer, o uso de GPU é altamente recomendado. A CPU limita a exploração prática, enquanto a GPU torna o processo factível em termos de tempo e permite maior aprofundamento nos experimentos.

## Modelo Transformer
### Pontos Positivos

- Capacidade de capturar dependências de longo prazo em sequências por meio do mecanismo de *self-attention*.  
- Treinamento mais eficiente em paralelo em comparação com arquiteturas recorrentes, devido à ausência de dependência sequencial.  
- Flexibilidade para ser adaptado a diferentes tarefas de processamento de linguagem natural (tradução, resumo, classificação, entre outras).  
- Estado da arte em diversas benchmarks de NLP, apresentando resultados superiores a modelos anteriores como RNNs e LSTMs.  

### Pontos Negativos 

- Elevado custo computacional, especialmente em tarefas com sequências longas, já que a complexidade do *self-attention* cresce quadraticamente com o tamanho da entrada.  
- Forte dependência de hardware acelerador (GPU ou TPU) para treinamento em tempo viável.  
- Necessidade de grandes volumes de dados para alcançar desempenho competitivo, o que pode dificultar experimentos em cenários de dados limitados.  
- Estrutura complexa, com múltiplas camadas e mecanismos que aumentam a dificuldade de interpretação e depuração do modelo.

O modelo Transformer representa um avanço significativo no processamento de linguagem natural, trazendo ganhos de desempenho e flexibilidade em relação a arquiteturas anteriores. Apesar do alto custo computacional e da necessidade de hardware especializado, mostra-se como a principal abordagem em tradução automática e outras tarefas de NLP.  
