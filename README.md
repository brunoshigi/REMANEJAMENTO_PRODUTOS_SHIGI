# Script de Remanejamento de Produtos entre Lojas

## Objetivo do Script

Este script foi desenvolvido com o objetivo de identificar oportunidades de remanejamento de produtos entre lojas. Ele visa garantir que as lojas que estão sem estoque de determinado produto possam ser reabastecidas a partir das lojas que possuem esse produto em quantidades excedentes.

## Critérios para Remanejamento

### 1. Produtos Zerados no Estoque Matriz
- **Premissa:** Produtos que estão com estoque zerado na matriz não serão repostos nas lojas.
- **Ação:** As lojas que ainda possuem estoque desses produtos devem considerar o remanejamento entre si, uma vez que esses produtos não serão mais enviados da matriz.

### 2. Identificação de Estoque Zero e Disponibilidade em Outras Lojas
- **Premissa:** Quando uma loja está com o estoque de um determinado produto zerado, mas esse produto ainda está disponível em outras lojas.
- **Ação:** Identificar essas situações para possibilitar o remanejamento de uma unidade do produto para a loja que está sem estoque.

### 3. Condição de Quantidade Mínima para Remanejamento
- **Premissa:** Apenas as lojas que possuem 2 ou mais unidades de um produto poderão enviar uma unidade para uma loja que está zerada.
- **Ação:** Garantir que o remanejamento ocorra sem esgotar o estoque da loja que está enviando o produto, mantendo pelo menos uma unidade em estoque.

### 4. Prioridade no Remanejamento
- **Premissa:** Quando mais de uma loja está sem estoque de um produto, a loja que deve receber a peça será aquela que teve o maior volume de vendas do produto em questão.
- **Ação:** Comparar as vendas do produto nas lojas com estoque zerado e priorizar a loja que vendeu mais unidades para receber o remanejamento.

## Passos para Implementação do Script

### 1. Carregamento dos Dados
- Ler a planilha de estoque e vendas para identificar os produtos com estoque zerado e a disponibilidade de produtos em outras lojas.

### 2. Filtragem de Produtos com Estoque Zerado
- Identificar todas as lojas onde o estoque de determinado produto está zerado.

### 3. Identificação de Lojas com Estoque Excedente
- Para cada produto com estoque zerado em alguma loja, verificar as lojas que possuem 2 ou mais unidades desse produto.

### 4. Definição de Prioridade para Remanejamento
- Se mais de uma loja está zerada para um determinado produto, calcular a prioridade de recebimento com base nas vendas históricas.

### 5. Geração da Lista de Remanejamento
- Criar uma lista com as recomendações de remanejamento, especificando:
  - Produto SKU
  - Loja de Origem (que enviará a peça)
  - Loja de Destino (que receberá a peça)
  - Quantidade a ser enviada (normalmente 1 unidade)

### 6. Exportação dos Dados
- Salvar a lista de remanejamento em um arquivo de saída, como um Excel ou CSV, para facilitar a execução do plano de remanejamento.

## Como Executar

1. Certifique-se de que os dados de estoque e vendas estejam atualizados na planilha de entrada.
2. Execute o script seguindo as instruções no código.
3. Verifique a lista gerada de remanejamentos e aplique as recomendações nas lojas correspondentes.

## Contribuições

Contribuições são bem-vindas! Se você tem sugestões de melhorias ou encontrou algum problema, sinta-se à vontade para abrir uma issue ou enviar um pull request.

## Licença

Este projeto está licenciado sob a [The Unlicense](LICENSE).
