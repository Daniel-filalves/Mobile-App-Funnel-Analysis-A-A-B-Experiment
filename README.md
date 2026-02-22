📊 Análise de Funil e Teste A/A/B -- Aplicação Mobile
====================================================

📌 Descrição do Projeto
-----------------------

Este projeto tem como objetivo analisar o comportamento dos utilizadores numa aplicação mobile através:

-   🔎 Construção de um **funil de eventos**

-   📈 Análise de conversões ao longo do percurso do utilizador

-   🧪 Avaliação estatística de um **teste A/A/B**

-   ✅ Verificação de impacto de uma alteração de design (mudança de fontes)

O estudo foi realizado com recurso a **Python**, utilizando bibliotecas como `pandas`, `matplotlib` e `scipy`.

* * * * *

🎯 Objetivos
------------

1.  Limpar e preparar os dados de eventos

2.  Identificar o período válido de análise

3.  Construir o funil de conversão

4.  Calcular taxas de conversão e abandono

5.  Validar o teste A/A (grupos 246 e 247)

6.  Avaliar o impacto do grupo de teste (248)

7.  Aplicar correção de Bonferroni para múltiplos testes

* * * * *

📂 Estrutura dos Dados
----------------------

O dataset contém registos de eventos da aplicação com as seguintes variáveis:

| Coluna Original | Novo Nome | Descrição |
| --- | --- | --- |
| EventName | event | Nome do evento |
| DeviceIDHash | user_id | Identificador único do utilizador |
| EventTimestamp | timestamp | Timestamp do evento |
| ExpId | exp_id | Grupo experimental |

Foi criada ainda:

-   `datetime` → conversão do timestamp

-   `date` → data extraída do datetime

* * * * *

🧹 Preparação dos Dados
-----------------------

-   Conversão do timestamp para formato `datetime`

-   Criação da coluna de data

-   Identificação do período com dados estáveis

-   Remoção de dias iniciais com volume residual de eventos

* * * * *

🔄 Funil de Conversão
---------------------

Eventos analisados:

1.  `MainScreenAppear`

2.  `OffersScreenAppear`

3.  `CartScreenAppear`

4.  `PaymentScreenSuccessful`

### 📊 Resultados do Funil

-   7 429 utilizadores iniciaram na aplicação

-   3 434 completaram o pagamento

-   Taxa de conversão global: **≈ 46,2%**

### 🔎 Principais Insights

-   Maior abandono ocorre entre:

    -   **MainScreenAppear → OffersScreenAppear** (~39,5%)

-   Após o carrinho, a maioria dos utilizadores conclui a compra

-   O problema principal está na fase inicial do percurso

* * * * *

🧪 Análise Experimental (A/A/B)
-------------------------------

### 🔹 Teste A/A (246 vs 247)

-   Objetivo: validar consistência do sistema experimental

-   Resultado: **nenhuma diferença estatisticamente significativa**

-   Conclusão: divisão de grupos equilibrada

### 🔹 Teste A/B (246+247 vs 248)

-   Comparação das proporções por evento

-   Nível de significância: α = 0,1

-   Correção de Bonferroni aplicada

#### 📌 Resultado Final:

Não foram encontradas diferenças estatisticamente significativas.

* * * * *

📈 Conclusão Geral
------------------

-   O funil apresenta perdas naturais e progressivas

-   O principal ponto crítico está na transição inicial

-   A alteração das fontes (grupo 248) **não teve impacto estatístico**

-   A decisão de implementação pode basear-se em critérios estéticos ou estratégicos, não comportamentais

* * * * *

🛠️ Tecnologias Utilizadas
--------------------------

-   Python 3

-   pandas

-   matplotlib

-   scipy

-   Jupyter Notebook

* * * * *

📁 Estrutura do Repositório
---------------------------

├── notebooks/\
│   └── funnel_analysis.ipynb\
├── data/\
│   └── logs_exp_us.csv\
├── README.md

* * * * *

🚀 Competências Demonstradas
----------------------------

-   Data Cleaning

-   Análise de Funil

-   Análise de Conversão

-   Testes Estatísticos (Z-test)

-   Correção para múltiplas comparações

-   Visualização de Dados

-   Interpretação de Resultados
