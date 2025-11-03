# Diagnóstico de Doenças Cardiovasculares com Machine Learning (UCI Dataset)

## 🎯 Objetivo do Projeto

Este projeto de Machine Learning (ML) visa desenvolver e avaliar modelos de classificação para prever a presença ou ausência de doença cardíaca em pacientes, utilizando o dataset da UCI (University of California Irvine).

O trabalho foca na Análise Exploratória de Dados (EDA) de atributos-chave, no pré-processamento adequado da variável alvo e na comparação de diferentes classificadores para encontrar o modelo de melhor desempenho.

## 💾 Conjunto de Dados

O projeto utiliza dois conjuntos de dados:

1.  **`df_uci` (Dados Clínicos):** Contém 303 registros e 14 atributos clínicos (idade, sexo, colesterol, pressão arterial, etc.) utilizados para o treinamento dos modelos de previsão.
2.  **`df_brasil` (Dados de Mortalidade):** Contém dados de mortalidade por doenças cardiovasculares no Brasil, utilizados para análise de contexto e EDA.

## 🛠️ Metodologia e Pipeline de ML

O projeto seguiu as seguintes etapas:

### 1. Pré-processamento e Limpeza

* **Binarização da Variável Alvo (`num`):** A variável `num`, que originalmente possuía 5 classes de gravidade (0 a 4), foi convertida para uma classificação binária: **0** (Ausência de Doença) e **1** (Presença de Doença).
* **Separação e Padronização:** Os dados foram divididos em conjuntos de treino e teste. O `StandardScaler` foi aplicado para padronizar os dados, o que é **crucial** para o bom desempenho de modelos baseados em distância, como o KNN.

### 2. Análise Exploratória de Dados (EDA) Aprofundada

Foram analisados novos atributos, com destaque para a relação com a doença:

* **`thalach` (Frequência Cardíaca Máxima):** O Boxplot indicou que pacientes sem doença cardíaca atingem frequências máximas significativamente mais altas, sugerindo **menor capacidade de esforço** em pacientes doentes.
* **`exang` (Angina Induzida por Exercício):** O Gráfico de Contagem confirmou que a **ausência de angina por exercício** está fortemente associada à ausência de doença.

### 3. Modelagem e Avaliação

Dois novos classificadores foram treinados e avaliados no conjunto de teste:

* **KNeighborsClassifier (KNN)**
* **GradientBoostingClassifier**

As métricas utilizadas para avaliação foram: Acurácia, Confusion Matrix e Classification Report (Precision e Recall).

## ✨ Principais Resultados e Conclusões

| Modelo Testado | Acurácia no Teste | Comentário |
| :--- | :--- | :--- |
| **KNN (KNeighborsClassifier)** | **0.9180** | **Melhor Desempenho.** A alta acurácia reforça a importância da padronização e a adequação do modelo à distribuição dos dados. |
| **GradientBoostingClassifier**| **0.8525** | (Desempenho ligeiramente inferior ao KNN, mas confirma a eficácia dos modelos baseados em árvores.) |

### Conclusão Estratégica
O modelo **KNN** demonstrou a melhor capacidade preditiva. No entanto, em um contexto clínico, a acurácia deve ser balanceada com o **Recall** (minimizar Falsos Negativos), que indica a segurança do modelo em capturar todos os pacientes realmente doentes.

## 💻 Como Rodar o Código

O projeto está contido no arquivo `.ipynb` (Jupyter Notebook).

1.  **Ambiente:** Certifique-se de ter as bibliotecas essenciais instaladas (Pandas, Numpy, Matplotlib, Seaborn, Scikit-learn).
2.  **Execução:** Execute o notebook sequencialmente. Ele fará o download dos dados automaticamente das URLs fornecidas.
