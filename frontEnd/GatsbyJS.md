# GatsbyJS

Gerador de site estático com uma estrutura de front-end moderna para criar
sites e aplicativos estáticos e que não depende de um servidor web, aplicando
se ao conceito Jamstack.

## O que é usado para contruir o site

* ReactJS
* GraphQL
* Webpack
* JavaScript

## Como usar

1. ``npm install --g gatsby-cli``
2. ``gatsby develop``

## Estrutura - Files

* gatsby-browser.js

Configurações do gatsby que afetam o navegador.

* gatsby-config.js

É o principal arquivo de configuração para um site do gatsby. Onde posso
especificar meta dados sobre o site, como título, descrição e os plugins do gatsby.

* gatsby-node.js

Configura caminhos relacionados ao site.

## Para criar as páginas estáticas e rotas

```file structure
project
│   README.md
│
└──src
   │
   └───pages
       │   index.js # /
       │   about.js # /about
       │   contact.js # /contact
       |   ...
```

## Conversão

Como todo código React é escrito em JSX uma extensão de sintaxe para JS, o código
é todo convertido em JS com ajuda do Babel já embutido no gatsby.

## Navegação

Usa se o componente Link próprio do gatsby para navegar entre as rotas do site.

## GraphQL

Permite que o Gatsby busque os dados de muitas fontes distints que vem no formato
de plugins.

:warning: GraphQL é apenas uma especificação, é um documento que diz como escrever
um dos servidores.

:warning: Nativamente, o Gatsby usa o GraphQL para buscar dados no **tempo de construção**
e não no **tempo de execução**

:warning: Gatsby suporta dois tipos de consultas GraphQL:

* Páginas de consultas ## executada dentro de um componente da página
* E consultas estáticas

:file_folder: Para poder ler arquivos localmente é usado uma dependência

``npm install --save gatsby-source-filesystem``
