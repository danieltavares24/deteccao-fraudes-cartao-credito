# 💳 Detecção de Fraudes em Cartões de Crédito com Machine Learning

Pipeline de Machine Learning para classificação de eventos raros e tratamento de dados desbalanceados.

## O Desafio Técnico

O objetivo deste projeto é identificar transações fraudulentas em cartões de crédito utilizando um dataset altamente desbalanceado (onde as fraudes representam apenas 0,17% do total de dados).
Em problemas de eventos raros, o maior desafio não é a acurácia, mas sim a capacidade do modelo em detectar a classe minoritária sem gerar um volume excessivo de falsos alarmes. Este projeto demonstra o domínio de técnicas avançadas de Data Cleaning, Feature Scaling e Resampling.

## Stack Tecnológica

* **Machine Learning:** Scikit-Learn
* **Interface Web:** Streamlit
* **Serialização do Modelo:** Joblib
* **Manipulação de Dados:** Pandas
* **Linguagem:** Python 3.x

## Metodologia e Engenharia de Dados

### **1.** Tratamento de Dados e Scaling 

Como as variáveis Time e Amount possuem escalas e magnitudes distintas das demais (que já passaram por uma transformação PCA), apliquei o RobustScaler. Essa técnica é ideal para dados com outliers, garantindo que o modelo não seja enviesado por valores extremos.

### **2.** Gerenciamento de Desbalanceamento (Imbalanced Data) 

Para evitar que o modelo apenas "aprendesse" a classe majoritária, foram implementadas e comparadas estratégias de:

Under-sampling: Redução da classe majoritária para equilibrar o dataset. 
Avaliação de Métricas: Foco em Recall e Precision, abandonando a métrica de Acurácia (que seria enganosa neste cenário).

### **3.** Avaliação de Performance 

O modelo foi validado utilizando Matrizes de Confusão e a curva AUPRC (Area Under the Precision-Recall Curve), que é a métrica mais robusta para conjuntos de dados desproporcionais.

## Modelo em Produção

* Deploy com Streamlit: O projeto conta com uma interface interativa onde o usuário pode inserir os dados da transação e receber a predição em tempo real. 
* Otimização com Joblib: Utilização da biblioteca Joblib para persistência do modelo, garantindo um carregamento eficiente e rápido dentro da aplicação.

## Resultados

* O pipeline conseguiu isolar as anomalias com alta taxa de Recall, garantindo que a maioria das fraudes fosse interrompida antes da liquidação. 
* A separação das classes via algoritmos de árvore demonstrou robustez mesmo antes da aplicação de técnicas de balanceamento agressivas.

## Conexão com a IA Industrial

Este projeto de Detecção de Fraudes é o alicerce para sistemas de Manutenção Preditiva. Na indústria, uma falha crítica em uma turbina ou motor é um evento tão raro quanto uma fraude. As técnicas aqui aplicadas (Detecção de Anomalias e Resampling) são as mesmas utilizadas para prever quebras de máquinas em linhas de produção a partir de sensores de vibração e temperatura.

## Estrutura do Repositório

* detecção_de_fraudes.ipynb: Notebook completo com análise exploratória (EDA) e treinamento. 
* requirements.txt: Dependências do projeto. 
* data/: (Link para o dataset original do Kaggle).

## Daniel Tavares de França
Cientista de Dados | Visão Computacional & Machine Learning
