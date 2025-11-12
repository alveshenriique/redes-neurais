# Repositório da Disciplina: Redes Neurais e Aprendizado Profundo

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Transformers-FFD21E?style=flat-square&logo=huggingface&logoColor=black)

## Sobre o Repositório

Este repositório contém todos os trabalhos práticos, anotações e projetos desenvolvidos para a disciplina de Redes Neurais e Aprendizado Profundo. O objetivo é aplicar os conceitos teóricos aprendidos em aula na construção de modelos de Machine Learning e Deep Learning.

---

### Informações da Disciplina

* **Universidade:** Universidade Federal de Viçosa - Campus Florestal
* **Curso:** Ciência da Computação
* **Professor(a):** Jose Augusto Miranda Nacif

---

## Trabalhos Práticos

Esta seção documenta o progresso e as entregas dos trabalhos práticos da disciplina.

### [Trabalho 01: Regressão Logística](./TP01-Regressao-Logistica/)

* **Objetivo:** Implementar um algoritmo de Regressão Logística do zero, usando apenas NumPy, para resolver um problema de classification binária de imagens (Gato vs. Não-Gato).
* **Conceitos Chave Aplicados:**
    * Pré-processamento de imagens (achatar e normalizar).
    * Implementação da Função Sigmoide.
    * Cálculo da Função de Custo (Entropia Cruzada Binária).
    * Implementação do Gradiente Descendente para otimização dos pesos.

### [Trabalho 02: Multilayer Perceptron e Backpropagation](./TP02-Backpropagation/)

* **Objetivo:** Construir uma rede neural de múltiplas camadas (MLP) com um número flexível de camadas. Foco na implementação do Backpropagation para treinar a rede e melhorar a acurácia em relação ao modelo anterior.
* **Conceitos Chave Aplicados:**
    * Implementação de Rede Neural Profunda (MLP).
    * Algoritmo de Backpropagation.
    * Função de Ativação ReLU.
    * Inicialização de pesos avançada.
    * Avaliação com Múltiplas Métricas (Acurácia, Precisão, Revocação, Matriz de Confusão).

### [Trabalho 03: Redes Neurais Convolucionais](./TP03-CNN/)

* **Objetivo:** Implementar uma Rede Neural Convolucional (CNN), especificamente a LeNet-5, utilizando PyTorch. Inclui a criação customizada das camadas de Convolução e MaxPooling (vetorizada) e treinamento com mini-batch gradient descent no dataset MNIST.
* **Entrega:** 21/10
* **Conceitos Chave Aplicados:**
    * Framework PyTorch (`nn.Module`, `DataLoader`, `transforms`).
    * Camadas Convolucionais (`nn.Conv2d`, `F.unfold`).
    * Camadas de Pooling (`nn.MaxPool2d`).
    * Construção de arquitetura CNN (LeNet-5).
    * Treinamento com Otimizador Adam e `CrossEntropyLoss`.
    * Batch Normalization e Dropout (no modelo opcional).

### [TP 04: Redes Neurais Recorrentes](./TP04-RNN/)

* **Objetivo:** Implementar uma Rede Neural Recorrente (RNN) simples em PyTorch para gerar nomes de Pokémon. Inclui também um desafio opcional para construir um modelo LSTM mais avançado para gerar texto no estilo de Machado de Assis, com foco no processamento de sequências, treinamento com validação e geração de texto.
* **Entrega:** 28/10
* **Conceitos Chave Aplicados:**
    * Implementação de Camada RNN customizada.
    * Criação de Vocabulário e Mapeamentos (char<->index).
    * PyTorch `Dataset` para sequências (one-hot e index encoding).
    * Treinamento de RNN/LSTM com `CrossEntropyLoss` e Adam.
    * Gradient Clipping (`clip_grad_norm_`).
    * Geração de texto (sampling) com `softmax` e `torch.multinomial`.
    * Camadas `nn.Embedding` e `nn.LSTM`.
    * Treinamento com loop de validação e salvamento do melhor modelo.
    * Análise de curvas de aprendizado (Overfitting).
    * Geração de texto com Top-K sampling.

### [Trabalho Prático Final (TPF): Reprodução de Artigo (DistilBERT)](./TPF-01-distilBERT/)

* **Objetivo:** Reproduzir os experimentos de *fine-tuning* do artigo **"DistilBERT, a distilled version of BERT: smaller, faster, cheaper and lighter"**. O projeto focou na tarefa de classificação binária de sentimentos (Positivo/Negativo) do dataset **SST-2** (do benchmark GLUE).
* **Entregas:** 04/11 (Proposta TPF-01) e 14/11 (Relatório TPF-02)
* **Conceitos Chave Aplicados:**
    * Utilização do ecossistema Hugging Face (`transformers`, `datasets`, `evaluate`).
    * Carregamento de modelos pré-treinados (`distilbert-base-uncased` via `AutoModelForSequenceClassification`).
    * Tokenização (`AutoTokenizer`) e pré-processamento de dados textuais.
    * Implementação do *fine-tuning* usando a API `Trainer` e `TrainingArguments`.
    * Cálculo de métricas (`accuracy`) e análise de resultados (comparação com o artigo original).
    * Análise de *overfitting* (monitoramento da `validation_loss`).
    * Gerenciamento de ambiente e resolução de conflitos de dependência no Google Colab.

---

## Tecnologias Utilizadas

* **Linguagem:** Python
* **Bibliotecas Principais:** NumPy, Matplotlib, PIL, Scikit-learn, PyTorch, Hugging Face (`transformers`, `datasets`, `evaluate`)
* **Ambiente de Desenvolvimento:** Google Colab
* **Controle de Versão:** Git & GitHub

---

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/henrique-alves-5237862ab/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/alveshenriique)
