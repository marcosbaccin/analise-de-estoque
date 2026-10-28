# Otimização de estoque com curvas ABC/XYZ

Dashboard interativo que cruza **valor** (curva ABC, pelo faturamento) com **regularidade de venda** (curva XYZ, pela frequência) para recomendar uma ação de compra a cada produto do catálogo de uma loja de varejo.

**Abra o dashboard:** baixe `index.html` e abra no navegador (precisa de internet para carregar gráficos e fontes), ou ative o GitHub Pages neste repositório.

## Aviso sobre os dados
Os dados são **anonimizados**. Nomes e códigos de produto foram trocados por IDs genéricos e os valores em reais (faturamento, lucro) e o volume foram multiplicados por um fator constante não divulgado. Por isso, percentuais, margens, classes e proporções entre produtos continuam fiéis ao original, mas os valores absolutos não são reais.

## Metodologia
- Base: 56.637 registros de vendas consolidados em 2.192 produtos únicos; dados de clientes anonimizados (LGPD).
- **Curva ABC** (faturamento): A = top 80%, B = próximos 15%, C = últimos 5%.
- **Curva XYZ** (dias distintos com venda): X = top 20%, Y = próximos 30%, Z = últimos 50%.
- **Ações:** Comprar mais (AX, AY, BX) · Manter (BY, CX) · Monitorar (AZ, BZ, CY e lançamentos CZ, com até 6 meses de histórico) · Parar de comprar (CZ com histórico maduro).
- **Estoque atual:** o código do produto foi cruzado com o cadastro atual da loja. Código ausente = fora do estoque atual. A quantidade em estoque não é considerada.

## Principais resultados
- 563 produtos (26% do catálogo) respondem por 79,5% do faturamento e 80,9% do lucro (recomendação "Comprar mais").
- 809 produtos são CZ (baixo valor e venda esporádica): 721 candidatos a "Parar de comprar" e 88 lançamentos em monitoramento.
- 823 produtos não constam mais no estoque atual, incluindo 91 com recomendação "Comprar mais", que merecem revisão antes de qualquer reposição.

## Arquivos
- `index.html`: dashboard (HTML + Chart.js, sem build).
- `data/recomendacoes_estoque_anonimizado.csv`: base anonimizada usada no dashboard.
