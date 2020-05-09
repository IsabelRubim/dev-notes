# Arquitetura Flux

## O que é Redux

* Biblioteca que implementa arquitetura flux
* Controle de estados globais (não tem dono)

## Quando utilizar o Redux

* Meu estado tem mais de um "dono"?
* Meu estado é manipulado por mais componentes?
* As ações do usuário causam efeitos colaterais nos dados?

Exemplos: carrinho de compras, dados do usuário, player de música, etc;

## Princípios

* Toda ação deve possuir um "type" (o type é único)
* O estado do Redux é o único ponto de verdade
* Não podemos realizar alterações no estado do Redux sem uma ação
* As ações e reducers são funções puras, ou seja, não lidam com side-effects assíncronos
* Qualquer lógica síncrona para regras de negócio deve ficar no reducer e nunca na ação

:warning: Nem toda aplicação precisa de Redux, inicie sem ele e sinta a necessidade depois.

### Dentro do reducer

* Ouvir as ações
* Manipular os estados da maneira que for necessário
