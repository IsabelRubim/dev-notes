# Conceitos de testes

## Testes unitários

Testam uma função mínima e pura, que não reliza efeitos colaterais, como acessos
ao banco ou integrações externas.

* **função mínima** - funcionalidade muito isolada da aplicação.
* **função pura** - não tem efeitos colaterais, como acessos ao banco ou integrações
externas, não faz chamadas api, dados os mesmos parâmetros sempre tem o mesmo retorno.

## Testes de integração

Os principais testes do back-end, testam funcionalidades completas como acesso à rotas
até o retorno do controller.

## Testes E2E (And Two And)

Testes de interface que simulam o acesso do usuário.

## TDD (Test Driven Development)

* Cria testes antes da funcionalidade
* Facilita visualização das regras de negócio

* **RED** - significa que seu teste falhou
* **GREEN** - significa que desenvolveu a feature
* **REFACTOR** - refatora o código

## Code Coverage

* Code Coverage coleta informações das linhas de código que seus testes atuais não
alcançaram.
* Utiliza uma tabela indicando o arquivo e a porcentagem

## Ferramenta para teste - JEST

JEST é uma estrutura de teste de JS.

* Framework de testes do facebook
* Trabalho tanto no back-end / front-end / mobile
* Tudo em um só pacote
* Code Coverage integrado
* Multi-thread integrado
