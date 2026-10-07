# Modelagem do Sistema

## Visão Geral

O sistema tem como objetivo cadastrar fornecedores, produtos e
cotações, permitindo comparar os preços oferecidos por diferentes fornecedores
para um produto específico.

Um fornecedor pode oferecer vários produtos, mas não é necessário que ofereça
todos os produtos cadastrados no sistema. Da mesma forma, um produto pode ser
oferecido por vários fornecedores.

A comparação deve considerar somente os fornecedores que possuem uma cotação
cadastrada para o produto escolhido.


## Fornecedor

### Responsabilidades

- Conhecer seu identificador único
- Conhecer seu nome
- Conhecer suas informações de contato
- Conhecer observações adicionais relacionadas ao fornecedor
- Estar associado às cotações realizadas pelo fornecedor

### Colaboradores

- Cotacao


## Produto

### Responsabilidades

- Conhecer seu identificador único
- Conhecer seu nome
- Conhecer sua categoria
- Representar um produto que pode ser oferecido por diferentes fornecedores
- Estar associado aos itens de cotação nos quais foi ofertado

### Colaboradores

- ItemCotacao


## Cotacao

### Responsabilidades

- Conhecer seu identificador único
- Conhecer o fornecedor responsável pela cotação
- Conhecer a data em que a cotação foi registrada
- Manter os itens pertencentes à cotação
- Representar uma cotação realizada por um único fornecedor
- Permitir que o fornecedor apresente preços apenas para os produtos que oferece

### Colaboradores

- Fornecedor
- ItemCotacao


## ItemCotacao

### Responsabilidades

- Conhecer seu identificador único
- Conhecer a cotação à qual pertence
- Conhecer o produto cotado
- Conhecer o preço unitário oferecido para o produto
- Relacionar um produto específico à cotação de um fornecedor
- Representar a oferta de um produto por determinado fornecedor

### Colaboradores

- Cotacao
- Produto


## ServicoCotacao

### Responsabilidades

- Centralizar as regras de negócio relacionadas às cotações
- Consultar ofertas cadastradas para um produto específico
- Consultar cotações realizadas por determinado fornecedor
- Comparar preços oferecidos para um produto
- Ordenar ofertas de acordo com critérios de comparação
- Identificar a melhor oferta disponível para um produto

### Colaboradores

- Produto
- ItemCotacao
- Cotacao
- Fornecedor
