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

-  Cadastro de produtos     -  Listagem de produtos
-  Edição de produtos       -  Exclusão de produtos
-  Cadastro de categorias   -  Produtos por categoria

###  Desafio 1 — Categorias
Criei o model Categoria em models/index.js e relacionei com Produto usando hasMany e belongsTo, com categoriaId como chave estrangeira.
Usei as: 'categoria' para definir o nome da associação.

As categorias são cadastradas em /categorias. Nos formulários de produto, um <select> permite escolher a categoria, e a listagem exibe seu nome.
### Desafio 2 — Produtos por categoria

Criei a rota GET /produtos/categoria/:id para listar os produtos de uma categoria. O id vem de req.params.id, e a categoria é buscada com findByPk, retornando 404 se não existir.

Os produtos são filtrados por categoriaId e exibidos em categoria.ejs. Na página /categorias, cada nome é um link para essa rota.
