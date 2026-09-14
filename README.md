# Classificação de Doenças em Folhas com Aprendizado de Máquina e Deep Learning

Projeto Final da disciplina **Modelagem de Análise e Aquisição de Padrões em IA — UniSales (2026/2)**.

## 👨‍🎓 Autor

**Hebert Souza Raphalsky Do Nascimento**

## 📌 Sobre o projeto

Este projeto apresenta um sistema de reconhecimento de padrões aplicado à **classificação de doenças e condições fitossanitárias em imagens de folhas**.

Foi utilizado o dataset **PlantVillage**, a partir de um subconjunto balanceado de **900 imagens**, distribuídas em **6 classes**, com 150 imagens por classe.

As imagens foram redimensionadas para **64×64 pixels** e normalizadas para o intervalo **[0,1]**.

## 🌱 Classes utilizadas

- Pimentão — Mancha bacteriana
- Pimentão — Saudável
- Batata — Requeima precoce
- Batata — Requeima tardia
- Batata — Saudável
- Tomate — Saudável

## 🔬 Metodologia

O projeto segue um pipeline de reconhecimento de padrões composto por:

1. Aquisição e seleção do dataset;
2. Análise exploratória dos dados (EDA);
3. Tratamento de valores inválidos;
4. Conversão para RGB;
5. Redimensionamento das imagens;
6. Normalização dos pixels;
7. Codificação das classes;
8. Redução de dimensionalidade com **PCA**;
9. Aplicação de **LDA** em um dos experimentos;
10. Divisão treino/teste considerando grupos de folhas;
11. Treinamento de **SVM**;
12. Ajuste de hiperparâmetros com **GridSearchCV**;
13. Treinamento de uma **Rede Neural Convolucional (CNN)**;
14. Avaliação por métricas de classificação;
15. Matrizes de confusão;
16. Curvas ROC/AUC;
17. Análise de erros;
18. Comparação dos modelos.

## 🤖 Modelos

### SVM + PCA

Modelo supervisionado obrigatório do roteiro. O SVM é treinado utilizando a representação reduzida pelo PCA.

### SVM + PCA + LDA

Segundo experimento clássico, utilizando PCA seguido de LDA para obter uma representação de menor dimensionalidade.

### CNN

Modelo de Deep Learning utilizado como segundo paradigma do projeto. A rede possui blocos convolucionais, pooling, camada densa, Dropout e uma camada de saída softmax com seis classes.

## 📊 Resultados da execução registrada

| Modelo | Accuracy | Precision | Recall | F1-Score |
|---|---:|---:|---:|---:|
| SVM + PCA | 70,17% | 70,70% | 70,17% | 69,22% |
| SVM + PCA + LDA | 69,61% | 69,40% | 69,61% | 69,28% |
| CNN | 65,75% | 67,10% | 65,75% | 60,17% |

Na execução registrada, **SVM + PCA apresentou o melhor desempenho geral no conjunto de teste**.

## 📈 Avaliação

O notebook apresenta:

- Accuracy;
- Precision;
- Recall;
- F1-Score;
- Matrizes de confusão;
- Curvas ROC;
- AUC;
- análise de erros e exemplos de classificações incorretas.

## ⚠️ Limitações

O PlantVillage contém imagens produzidas em condições relativamente controladas. Portanto, um bom resultado nesse dataset não garante o mesmo desempenho em fotografias obtidas diretamente no campo.

Além disso, este projeto utiliza somente seis classes das 38 classes disponíveis no conjunto completo. Os resultados, portanto, não representam todas as doenças presentes no PlantVillage.

O sistema deve ser interpretado como um **experimento acadêmico de reconhecimento de padrões**, e não como uma ferramenta de diagnóstico agronômico definitivo.

## 📁 Estrutura sugerida do repositório

```text
PlantVillage-Projeto-Final/
│
├── README.md
├── PlantVillage_Projeto_Final_COMENTADO.ipynb
└── resultados/
    ├── matriz_confusao_svm.png
    ├── matriz_confusao_cnn.png
    ├── roc_svm.png
    └── roc_cnn.png
```

Os arquivos de resultados podem ser adicionados caso sejam exportados do notebook.

## ▶️ Como executar

O notebook foi desenvolvido para execução em ambiente compatível com Python/Jupyter, incluindo Google Colab.

1. Abra o arquivo `.ipynb`;
2. Instale/garanta as dependências utilizadas no notebook;
3. Execute as células na ordem;
4. Disponibilize o dataset conforme indicado no próprio notebook;
5. Execute o pipeline completo para reproduzir os resultados.

## 📚 Referências principais

- HUGHES, David P.; SALATHÉ, Marcel. *An open access repository of images on plant health to enable the development of mobile disease diagnostics through machine learning and crowdsourcing*. 2015.
- MOHANTY, Sharada P.; HUGHES, David P.; SALATHÉ, Marcel. *Using deep learning for image-based plant disease detection*. Frontiers in Plant Science, 2016.
- CORTES, Corinna; VAPNIK, Vladimir. *Support-vector networks*. Machine Learning, 1995.
- JOLLIFFE, Ian T.; CADIMA, Jorge. *Principal component analysis: a review and recent developments*. Philosophical Transactions of the Royal Society A, 2016.
- HASTIE, Trevor; TIBSHIRANI, Robert; FRIEDMAN, Jerome. *The Elements of Statistical Learning*. 2. ed. Springer, 2009.

## 📄 Entrega acadêmica

Este repositório complementa o relatório técnico do Projeto Final e disponibiliza o código-fonte utilizado no experimento, conforme solicitado no roteiro da disciplina.
