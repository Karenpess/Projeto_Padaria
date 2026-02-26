## Análise de Dados SAF-T Padaria.

### Visão Geral

Este projeto apresenta uma análise exploratória de dados provenientes do sistema **SAF-T (Standard Audit File for Tax)**, com foco na transformação, modelagem e geração de insights de negócios acionáveis para uma padaria. 

O objetivo foi estruturar um pipeline de dados completo, desde a limpeza e organização até análises e recomendações.

### Objetivos do Projeto

* Construir um pipeline de tratamento de dados SAFT
* Estruturar dados para análise de vendas
* Identificar padrões de consumo
* Calcular métricas estratégicas (ticket médio, top produtos, sazonalidade)
* Realizar análise ABC de produtos
* Detectar possíveis anomalias
* Produzir um sumário executivo para tomada de decisão

### Estrutura do Projeto
1. Extração e Preparação dos Dados

* Remoção de prefixos (ex: `ns1:`)
* Exclusão de colunas de sistema e auditoria interna
* Tratamento de valores ausentes
* Padronização de tipos de dados
* Criação de colunas de interesse para a análise
* Criação de identificador único por linha

2. Modelagem dos Dados

Organização das informações em três grupos principais:
* Informações de Produto
* Informações Fiscais
* Informações de Venda

Validações realizadas:
* Consistência entre colunas duplicadas
* Remoção de linhas vazias
* Remoção de linhas irrelevantes para a análise (`Quantity` <= 0 ou `UnitPrice` < 0)
* Ajustes em códigos fiscais

3. Análise Exploratória (EDA)

* Criação da coluna `GrossValue` a partir do valor unitário, quantidades e taxas
* Criação das colunas `Hora`, `Dia`, `Dia_Semana`, `Mês` e  `Ano` a partir de `MovementStartTime` 

Principais análises realizadas:

Evolução de vendas ao longo do tempo

* Top produtos
* Vendas por dia da semana
* Ticket médio
* Distribuição de faturamento

4. Análises Estratégicas

* Análise ABC de Produtos
    Classificação de produtos em:
    * Classe A (acima de 95%)
    * Classe B (acima de 80%)
    * Classe C (acima de 60%)

* Análise de Categorias
    Avaliação do desempenho por grupos de produtos.

* Identificação de Anomalias
    Busca por padrões incomuns em:
    * Valores
    * Frequência de vendas
    * Movimentação financeira

5. Dashboard Executivo
Criação de visualizações consolidadas para apoio à tomada de decisão.

6. Sumário Executivo
Documento separado com:
* Principais insights
* Pontos de atenção
* Recomendações estratégicas


### Tecnologias Utilizadas
* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn 
* Jupyter Notebook

### Principais Métricas Analisadas
* Faturamento total
* Ticket médio
* Volume de vendas
* Produtos mais vendidos
* Concentração de receita (ABC)
* Padrões temporais de consumo
* O fluxo de trabalho foi dividido em quatro pilares fundamentais:

### Principais Insights
* Alta concentração de receita em poucos produtos (efeito 80/20).
* Determinados dias da semana apresentam maior volume de vendas.
* Produtos Classe A representam a maior parte do faturamento.
* Identificação de possíveis inconsistências fiscais ou operacionais.

---

**Autor:** Karen Pessoa

**Projeto:** Análise de Dados SAF-T Padaria. 
