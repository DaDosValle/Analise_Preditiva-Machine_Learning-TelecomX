# Análise Preditiva de Churn -- TelecomX

## Visão Geral

Este projeto tem como objetivo desenvolver um modelo preditivo capaz de
identificar clientes com alta probabilidade de evasão (churn) em uma
empresa de telecomunicações.

A retenção de clientes é um dos principais desafios do setor, pois o
custo de adquirir novos clientes é significativamente maior do que
manter os atuais. Assim, prever churn permite direcionar ações
estratégicas de retenção e reduzir perdas financeiras.

------------------------------------------------------------------------
## Problema de Negócio

A TelecomX enfrenta uma taxa de churn de aproximadamente 27%, o que representa perdas financeiras significativas.

#### Perguntas Centrais do Estudo

- Quem são os clientes com maior risco de evasão?
- Quais variáveis mais influenciam esse comportameto?
- Que tipo de perfil a empresa precisa manter mais próximo?

------------------------------------------------------------------------

## Objetivos do Projeto

-   Identificar os principais fatores associados ao churn.
-   Desenvolver e comparar modelos de machine learning.
-   Avaliar desempenho utilizando métricas apropriadas para dados
    desbalanceados.
-   Estimar o impacto financeiro potencial da implementação do modelo.
-   Gerar insights estratégicos para tomada de decisão.

------------------------------------------------------------------------

##  Estrutura do Projeto
 Analise_Preditiva_TelecomX\
│\
├── 📄 Analise_Preditiva_TelecomX.ipynb (estudo e relatório)\
├── 📄 README.md\
└── 📄 dados_tratados.csv

------------------------------------------------------------------------

## 🗂️ Descrição das Variáveis Principais

-   `churn` → Variável alvo (0 = permanece, 1 = evadiu)\
-   `tipo_contrato` → Mensal, Um ano, Dois anos\
-   `tempo contrato` → Tempo de permanência em meses\
-   `suporte tecnico` → Indica se o cliente utiliza suporte técnico\
-   `cobrancas mensais` → Valor da mensalidade

------------------------------------------------------------------------

## 🔍 Análise Exploratória

Principais insights identificados:

-   Contratos mensais apresentam maior concentração de churn.
-   Clientes com menor tempo de contrato possuem maior probabilidade de
    evasão.

-   A falta de uso do suporte técnico pode indicar maior churn.

-  O risco é mais elevado nos primeiros meses de contrato.

-  Clientes com maior custo mensal apresentam maior probabilidade de evasão.



------------------------------------------------------------------------

## ⚙️ Modelagem Preditiva

### 🔄 Pipeline Utilizado

-   StandardScaler\
-   SMOTE (tratamento de desbalanceamento)\
-   Modelos de classificação

Exemplo:

``` python
Pipeline(steps=[
    ('scaler', StandardScaler()),
    ('smote', SMOTE(random_state=42)),
    ('modelo', LogisticRegression(max_iter=1000))
])
```

------------------------------------------------------------------------

## 🤖 Modelos Avaliados

-   Regressão Logística\
-   Árvore de Decisão\
-   Random Forest\


------------------------------------------------------------------------

## 📏 Métricas de Avaliação

-   ROC-AUC\
-   Precision\
-   Recall\
-   F1-Score\
-   Cross-Validation (Stratified K-Fold)

Métrica principal escolhida: Recall

Justificativa:

Em churn, o custo do falso negativo (não identificar um cliente que irá sair) é alto.
Portanto, priorizou-se maximizar o recall para capturar o maior número possível de clientes em risco.

Resultado do modelo:

Recall: 81%

Isso significa que o modelo identifica 81% dos clientes que realmente cancelariam.

------------------------------------------------------------------------

## 💰 Simulação do Impacto Financeiro

Simulação baseada em:

-   Base estimada de 10.000 clientes\
-   Ticket médio mensal\
-   Taxa real de churn observada

Com aplicação do modelo e ações de retenção direcionadas, é possível
reduzir perdas financeiras e gerar economia anual significativa.



Foram simulados três cenários:

 - Cenário Atual

2.700 clientes churn

Perda estimada: R$ 405.000

- Cenári 2: Modelo + 30% de retenção sobre recall

Recuperação parcial dos clientes identificados

Economia estimada: ~R$ 97.200

- Cenári 3: Modelo + 100% de retenção sobre recall

Recuperação total dos clientes identificados

Economia estimada: ~R$ 328.050

------------------------------------------------------------------------

## 📈 Melhorias Futuras

-   Feature engineering adicional\
-   Teste de modelos mais robustos (XGBoost, LightGBM)\
-   Deploy em ambiente de produção

------------------------------------------------------------------------

## 🛠️ Tecnologias Utilizadas

-   Python\
-   Pandas\
-   NumPy\
-   Matplotlib\
-   Seaborn\
-   Scikit-Learn\
-   Imbalanced-learn

------------------------------------------------------------------------

## 👨‍💻 Conclusão Estratégica

A implementação do modelo preditivo, mesmo com taxa de retenção parcial (30%), já gera impacto financeiro relevante.

Com estrutura de retenção eficiente, o modelo pode reduzir drasticamente perdas associadas ao churn.



------------------------------------------------------------------------

## 👨‍💻 Autor

Fernando do Valle\
[Meu Linkedin](http://linkedin.com/in/fernando-do-valle/)

Cientista de Dados Jr (em formação Oracle-Alura)\
Analista de Dados Jr (Google e Meta)\
Marketing Digital (Unir - Universidad de La Rojas)
