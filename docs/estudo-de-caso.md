# Onde o volume de vendas esconde baixa rentabilidade?

Estudo de caso de portfólio · Python, pandas, Matplotlib e Jupyter

## Problema e contexto

Uma análise de faturamento pode destacar categorias que vendem muito e ainda
assim esconder operações deficitárias. A pergunta deste projeto foi: **quais
grupos merecem uma revisão de preços e custos primeiro?**

A base é a amostra histórica Superstore: **9.994 linhas de venda, 5.009 pedidos**,
de 2014 a 2017. O arquivo veio com o projeto; sua origem upstream e licença não
estão documentadas. Não se trata de um diagnóstico de uma empresa atual.

## Como a investigação foi feita

1. Auditar esquema, campos vazios, duplicatas, datas e consistência dos pedidos.
2. Separar linhas de pedidos distintos e definir a margem como
   **soma do lucro registrado / soma das vendas**.
3. Comparar categorias e subcategorias por resultado líquido e perdas brutas.
4. Investigar Tables por região, desconto e produto, exibindo o tamanho das
   amostras e as combinações sem observações.
5. Reconciliar os totais das tabelas com a base e executar o notebook inteiro
   em uma sessão nova, com validação automática no GitHub Actions.

Uma descoberta da auditoria foi que **32 códigos de produto têm nomes diferentes**.
O ranking usa pares de código/nome como identificadores provisórios; a análise
não presume que o cadastro de produtos esteja saneado.

## Evidências principais

| Evidência | O que ela permite concluir |
| --- | --- |
| US$ 2,30 milhões em vendas e US$ 286.397 de lucro registrado; margem de 12,47% | O agregado é positivo, sem demonstrar saúde financeira de toda a operação. |
| Furniture tem margem de 2,49% | O volume vendido nessa categoria merece investigação por subcategoria. |
| Tables registra −US$ 17.725 líquidos em 319 linhas | É o pior resultado líquido entre as subcategorias. |
| Binders acumula US$ 38.510 em perdas brutas, apesar de +US$ 30.222 líquidos | Olhar somente subcategorias negativas esconderia vendas deficitárias relevantes. |
| Tables com desconto ≥40% registra −US$ 27.296 em 122 linhas | É um grupo concreto para auditar preços, custos e regras de desconto. |
| Não há Tables sem desconto na região East | Falta uma comparação local para atribuir sua perda apenas aos descontos. |

![Margem por região e desconto, com contagens e células sem observações](../reports/figures/tables_region_discount.png)

Os recortes de região, desconto e produto se sobrepõem. Seus prejuízos não podem
ser somados como oportunidades independentes. Perdas brutas também não equivalem
a economias recuperáveis: retirar uma venda ou mudar seu preço pode alterar a demanda.

## Recomendação e resultado da entrega

A recomendação é **revisar as transações de Tables com descontos elevados**,
confirmar a composição dos custos e o cadastro de produtos, e só então testar
uma mudança de preços acompanhando unidades, demanda e margem de contribuição.
O mesmo diagnóstico pode ser estendido a Binders e Machines.

O resultado entregue é uma investigação reproduzível, quatro gráficos e seis
tabelas exportáveis, incluindo todos os 57 pares de produto de Tables. O recorte
de pelo menos cinco linhas seleciona 37 pares para leitura; esse limite é apenas
uma regra de apresentação, não significância estatística.

**Não foi implementada uma intervenção comercial nem medido aumento de lucro.**
Os dados são observacionais e não documentam integralmente custos, retornos,
estoque ou resposta da demanda aos preços. As recomendações são hipóteses para
investigar, não estimativas causais.

## Para apresentar em uma entrevista

Em cerca de 90 segundos: apresente a pergunta de negócio, explique por que
linhas não são pedidos, compare Tables com Binders, mostre uma célula ausente
no gráfico e termine com a decisão que ainda exige dados ou um experimento.

Esteja preparado para explicar por que a margem usa somas, por que perdas brutas
diferem do resultado líquido e por que um grupo com prejuízo não vira
automaticamente uma previsão de lucro recuperado.

## Conferir e reproduzir

- [Notebook executado e verificações](../notebooks/01_analysis.ipynb)
- [Resultados por subcategoria](../reports/tables/subcategory_performance.csv)
- [Tables por região e desconto](../reports/tables/tables_region_discount.csv)
- [Revisão completa dos produtos](../reports/tables/tables_product_review.csv)
- [Instalação, execução e limites da base](../README.md)
