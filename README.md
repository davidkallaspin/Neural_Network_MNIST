# Projeto de Classificação de Dígitos MNIST: Construindo e Comparando Redes Neurais em R

## 1. Resumo:

Esse projeto foi elaborado com o objetivo de praticar o desenvolvimento de redes neurais em Machine Learning usando a base de dados MNIST para classificação de dígitos manuscritos usando R. Durante o projeto, foram elaboradas duas redes neurais, a primeira uma Rede Neural Densa (MLP) e posteriormente uma Rede Neural Convolucional (CNN). Durante o desenvolvimento, a ideia foi explorar diferentes hiperparâmetros e complexidades de arquiteturas para as redes neurais a fim de testar e compreender como cada uma delas pode performar e exigir diferentes níveis de processamento computacional. Ao final, foi possível avaliar por meio das métricas (accuracy e loss) a performance de cada modelo e observar onde os erros foram cometidos.

## 2. Base de dados:

O conjunto de dados MNIST (Modified National Institute of Standards and Technology) é um dataset padrão da indústria para avaliação de algoritmos de reconhecimento de imagens. Ele consiste em 70.000 imagens em tons de cinza (60.000 para treinamento e 10.000 para teste) de dígitos manuscritos (0 a 9), cada uma com 28x28 pixels.

## 3. Etapas:

Este repositório contém o código em R que implementa:
- Carregamento e pré-processamento de dados.
- Construção, treinamento e avaliação de uma Rede Neural Densa (MLP).
- Construção, treinamento e avaliação de uma Rede Neural Convolucional (CNN).
- Utilização de **Early Stopping** para otimização do treinamento e prevenção de overfitting.
- Análise e comparação das métricas de desempenho de ambos os modelos.

## 2. Highlights:

### 2.1 Amostragem dos dados
Aqui está uma amostra de como são os dígitos que as redes precisam classificar. Cada pixel da imagem tem um valor inteiro entre 0 e 255, representando a intensidade do cinza.

![image](https://github.com/user-attachments/assets/6e1580e8-ecee-4a66-b45e-10ec61762c87)

### 2.2 Avaliação e Interpretação dos Resultados dos Modelos:

#### 2.2.1 Rede Neural Densa (MLP):

Abaixo, temos a visão de como o modelo aprendeu e generalizou ao longo da épocas:

![Captura de Tela 2025-06-15 às 12 18 11](https://github.com/user-attachments/assets/825f49a3-fe22-4416-8c39-d2ec8e04a8e8)

Temos uma rápida melhoria na acurácia e queda na perda, tanto no treino quanto na validação. As curvas se mantêm próximas, indicando boa generalização e um aprendizado eficiente pela Rede Neural Densa.

#### 2.2.2 Rede Neural Convolucional (CNN):

![image](https://github.com/user-attachments/assets/9dc1b384-2ec5-493b-881b-0f255dce381f)

Para a Rede Neural Convolucional, temos uma performance muito superior à MLP, com acurácia de validação atingindo rapidamente patamares acima de 99% e perdas minimizadas. Isso reflete a eficácia da arquitetura convolucional para dados de imagem. Podemos observar também que nas épocas finais a perda de validação tende a se estabilizar ou subir levemente enquanto a perda de treino continua caindo, um indicativo de que o modelo estava começando a sobreajustar. O early stopping por sua vez, foi importante aqui para parar o treinamento no ponto de melhor generalização do modelo evitando o overfitting.

### 2.3 Visualização dos Erros Cometidos pelo Modelo:

![image](https://github.com/user-attachments/assets/740f40bc-1e78-4b55-b611-c12d080075f9)

Aqui, podemos observar os erros cometidos pelo modelo CNN, o qual foi o de melhor performance apresentada, com uma acurácia de, aproximadamente 99%, ou seja, 1 erro a cada 100 previsões.

### 2.4 Conclusão Final:

- Ficou muito claro o porquê as CNNs são a escolha preferencial para problemas de visão computacional. Uma vez que, apresentaram performance superior em comparação com uma MLP.
A CNN não só entregou uma acurácia maior no conjunto de teste, como também mostrou uma convergência mais rápida e estável durante o treinamento.

- A implementação do Early Stopping foi importante para evitar o overfitting e reduzir tempo de processamento. O modelo estava no seu melhor equilíbrio entre aprender e generalizar, evitando que continuasse a treinar e talvez sobreajustar aos dados de treinamento. Sem ele, poderíamos ter pego um modelo ligeiramente menos otimizado.

- A visualização dos erros da CNN foi bastante interessante para trazer um entendimento mais concreto da base e de como existem dígitos "confusos" que podem levar a inconsistências. Mesmo com alta acurácia, é sempre interessante ver onde o modelo ainda "tropeça".

- As redes neurais, em sua estrutura de 'black box' possuem hiperparâmetros que devem ser explorados e testados para que somente assim, a melhor arquitetura seja alcançada.
