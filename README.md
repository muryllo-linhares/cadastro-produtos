#  Cadastro de Produtos — MVC

##  Integrante

MURYLLO LINHARES — RM 20250622

## Como executar

1. Instale as dependências:

```bash
npm install
```

2. Inicie o servidor:

```bash
npm start
```

3. Acesse no navegador: http://localhost:3000/produtos


##  Funcionalidades

-  Cadastro de produtos
-  Listagem de produtos
-  Edição de produtos
-  Exclusão de produtos
-  Cadastro de categorias
-  Produtos por categoria

##  Desafios

###  Desafio 1 — Categorias

Criei o model Categoria, com o campo nome, em models/index.js,
e estabeleci seu relacionamento com o model Produto por meio de Categoria.hasMany(Produto) e Produto.belongsTo(Categoria).
A tabela Produtos utiliza categoriaId como chave estrangeira.

Também defini as: 'categoria' na associação para controlar o nome da propriedade retornada nas consultas.

As categorias podem ser cadastradas pela rota /categorias. Nos formulários de criação e edição de produtos, 
foi adicionado um <select name="categoriaId"> que lista as categorias disponíveis. Na listagem de produtos,
utilizei include para carregar e exibir o nome da categoria associada a cada produto.

###  Desafio 2 — Produtos por categoria

Criei a rota GET /produtos/categoria/:id para consultar os produtos vinculados a uma determinada categoria.
Optei pelo método GET porque a rota apenas realiza uma consulta, sem alterar os dados.

A categoria é identificada pelo id, obtido por meio de req.params.id. Primeiro, a categoria é localizada utilizando findByPk.
Caso ela não exista, a aplicação retorna o status 404. Em seguida,
os produtos são buscados com Produto.findAll({ where: { categoriaId } }), filtrando os registros pela chave estrangeira categoriaId.

O resultado da consulta é exibido na view views/produtos/categoria.ejs. Na página /categorias, 
o nome de cada categoria funciona como um link que direciona para a respectiva rota, permitindo visualizar os produtos associados àquela categoria.
