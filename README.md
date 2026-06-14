#📊 Projeto-Analise-Churn-Telecom: Do tratamento de Dados ao Business Intelligence
---
## 🎯 Objetivo do Projeto
Este projeto foi desenvolvido com o objetivo de analisar e diagnosticar a perda de clientes (**Churn**) em uma empresa do setor de Telecomunicações. A meta foi identificar os principais gargalos que motivam o cancelamento dos serviços e mensurar o impacto financeiro dessas perdas, fornecendo insights estratégicos para os times de negócios e retenção.

---

## 🛠️ Tecnologias Utilizadas
* **Python** 
* **Pandas** (Tratamento, limpeza e manipulação de dados)
* **Power BI Desktop** (Modelagem dimensional e construção do dashboard)
* **DAX** (Criação de métricas de performance e financeiras)

---

## ⚙️ Processo de ETL e Modelagem Dimensional
1. Tratamento de Dados (Python & Pandas)
Antes de iniciar as análises, os dados passaram por uma etapa rigorosa de limpeza no arquivo tratamento_dados.ipynb:

Correção de Tipos: Conversão da coluna TotalCharges para numérico, tratando inconsistências de texto.

Tratamento de Nulos: Identificação e preenchimento de valores nulos na receita total baseados no tempo de casa (tenure = 0).

Transformação de Variáveis: Conversão de colunas textuais binárias (Churn, Partner, Dependents) em valores numéricos inteiros (0 e 1).

2. Modelagem de Dados (Star Schema)
Para garantir a performance máxima do Power BI, a tabela única original foi desnormalizada em uma arquitetura Star Schema (Esquema Estrela) composta por 1 Tabela Fato e 3 Tabelas Dimensão, conectadas via customerID:

fato_churn: Armazena as métricas e chaves (tenure, MonthlyCharges, TotalCharges, Churn).

dim_clientes: Atributos demográficos (Gênero, Idoso, Parceiro, Dependentes).

dim_servicos: Produtos e serviços de valor agregado contratados (Internet, Suporte Técnico, Telefone, etc.).

dim_contrato: Regras comerciais (Tipo de contrato, Método de pagamento, Faturamento digital).

---
## 📈 Principais Insights de Negócio
Com o dashboard finalizado e sem filtros aplicados, foram extraídos os seguintes indicadores e diagnósticos:

🌟 Métricas Globais (KPIs)
Total de Clientes Analisados: 7 Mil

Taxa de Churn Geral: 26,5%

Faturamento Mensal Atual (MRR): R$ 25,0 Milhões

Receita Perdida com Cancelamentos: R$ 7,7 Milhões

🔍 Principais Alertas Encontrados
O Combo Crítico (Matriz de Risco): Clientes com contrato mensal (Month-to-month) que utilizam internet de Fibra Óptica possuem uma taxa de cancelamento alarmante de 54,61%. Esse é o maior ponto de perda de receita da empresa.

A Curva de Permanência: O maior risco de evasão está concentrado no primeiro mês de contratação (61,99% de churn). Conforme o cliente ultrapassa a barreira dos 20 meses de casa, a taxa se estabiliza.

Impacto do Suporte Técnico: Clientes que não possuem suporte técnico contratado apresentam uma taxa de churn de 41,64%, contra apenas 15,17% daqueles que têm o serviço ativo.

---

## 🚀 Recomendações Estratégicas para o Negócio
Campanha de Migração de Contrato: Desenvolver uma estratégia de incentivo comercial para migrar clientes de contratos mensais de Fibra Óptica para planos anuais, reduzindo o churn desse grupo pela metade.

Onboarding Guiado no Mês 1: Criar um programa de acompanhamento intensivo para novos clientes nos primeiros 30 dias, período onde a taxa de cancelamento atinge o pico de 61,99%.

Inclusão de Suporte Técnico como Benefício: Oferecer o serviço de Suporte Técnico de forma gratuita nos primeiros meses de contrato para aumentar o engajamento e blindar a base de clientes.
