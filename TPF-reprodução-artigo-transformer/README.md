# TPF: Fine-Tuning e Otimização do DistilBERT

Este diretório contém os notebooks e a documentação técnica referente ao Trabalho Prático Final. O projeto foca na reprodução e subsequente otimização arquitetural do modelo `distilbert-base-uncased` na tarefa de classificação de sentimentos (GLUE/SST-2).

## Conteúdo do Diretório

| Arquivo | Descrição Técnica |
| :--- | :--- |
| **`TPF-02_Reproducao_Original.ipynb`** | Implementação *Full Fine-Tuning*. |
| **`TPF-03_DistilBERT_Otimizado.ipynb`** | Implementação com **Backbone Freezing** Camadas 0-3 congeladas e **Cosine Scheduler**. |
| **`Relatorio_Tecnico.pdf`** | Documentação formal com análise comparativa e referências teóricas. |

---

## Requisitos de Sistema

Para garantir a reprodutibilidade dos resultados e evitar conflitos de versões de bibliotecas (especialmente `transformers` vs. `accelerate`), o código foi projetado para execução em ambiente **Google Colab** com GPU.

* **Hardware Recomendado:** GPU NVIDIA T4 ou superior. O treinamento em CPU é inviável para este projeto ~11h/execução.
* **Dependências Críticas:** O notebook realiza a instalação automática forçada das seguintes versões:
    * `transformers==4.44.2`
    * `datasets==2.20.0`
    * `evaluate==0.4.2`
    * `scikit-learn==1.5.1`

---

## Guia de Execução Google Colab

Siga os passos abaixo para executar qualquer um dos notebooks (`.ipynb`):

1. **Upload:**
   - Acesse o [Google Colab](https://colab.research.google.com/).
   - Faça o upload do arquivo `.ipynb` desejado (TPF-02 ou TPF-03).

2. **Configuração do Runtime (Crítico):**
   - No menu superior, vá em `Ambiente de execução` > `Alterar tipo de ambiente de execução`.
   - Em **Acelerador de hardware**, selecione **T4 GPU**.
   - *Nota: Sem a GPU, o script emitirá um alerta e a execução será excessivamente lenta.*

3. **Instalação do Ambiente:**
   - Execute a **primeira célula** de código.
   - **Atenção:** O script forçará o reinício do kernel (`os.kill`) automaticamente para aplicar as atualizações de biblioteca. Isso é o comportamento esperado.

4. **Treinamento e Validação:**
   - Execute as células subsequentes em ordem.
   - O treinamento do TPF-02 leva aprox. **12-15 minutos**.
   - O treinamento do TPF-03 leva aprox. **8-10 minutos**.

---

## Especificações Técnicas dos Experimentos

Resumo das configurações utilizadas em cada etapa do projeto:

### Experimento 1: Reprodução
* **Estratégia:** Full Fine-Tuning 100% dos parâmetros treináveis.
* **Optimizer:** AdamW (`learning_rate=2e-5`, `weight_decay=0.01`).
* **Scheduler:** Linear Decay.
* **Batch Size:** 16.
* **Epochs:** 3.

### Experimento 2: Otimização
* **Estratégia:** Transfer Learning com Congelamento Parcial.
    * *Embeddings*: Congelados.
    * *Transformer Layers 0-3*: Congeladas.
    * *Transformer Layers 4-5*: Treináveis.
    * *Classifier Head*: Treinável.
* **Optimizer:** AdamW (`learning_rate=3e-5`).
* **Scheduler:** Cosine Annealing with Warmup (`warmup_ratio=0.1`).
* **Epochs:** 4 (Ajustado para o ciclo cosseno).

---

## Resultados Obtidos

| Métrica | Baseline Artigo | TPF-02 Reprodução | TPF-03 Otimização |
| :--- | :---: | :---: | :---: |
| **Acurácia (Val)** | 91.3% | **90.37%** | 89.22% |
| **Validation Loss** | - | 0.3102 | **0.2908** |
| **Eficiência** | - | ~15 min (GPU) | **~9 min (GPU)** |

