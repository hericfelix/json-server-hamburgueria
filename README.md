# KenzieBurger API

==========================

API que possui uma listagem de produtos de hamburgueria, e um carrinho de compras.

## Endpoints

==========================

A aplicação possui um total de 4 endpoints:

### Cadastro

==========================

`POST /register`

Endpoint de cadastro de novos usuários. A requisição deverá ser feita com o e-mail e o login no corpo.

```json
{
  "email": "teste@teste.com",
  "password": "teste123"
}
```

Caso tudo dê certo a resposta será assim:

`POST /register - STATUS 201`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXJAbWFpbC5jb20iLCJpYXQiOjE2MzUxODUwMjgsImV4cCI6MTYzNTE4ODYyOCwic3ViIjoiMyJ9.OOGgjbYHjAQ1AliVW39IY9_s4HpdxOlt4hEojm_fXYA",
  "user": {
    "email": "teste@teste.com",
    "id": 3
  }
}
```

### Login

==========================

`POST /login`

Endpoint de login de usuários já criados. A requisição deverá ser feita com o e-mail e o login no corpo.

```json
{
  "email": "teste@teste.com",
  "password": "teste123"
}
```

Caso tudo dê certo a resposta será assim:

`POST /login - STATUS 201`

```json
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6Im9saXZpZXJAbWFpbC5jb20iLCJpYXQiOjE2MzUxODUwMjgsImV4cCI6MTYzNTE4ODYyOCwic3ViIjoiMyJ9.OOGgjbYHjAQ1AliVW39IY9_s4HpdxOlt4hEojm_fXYA",
  "user": {
    "email": "teste@teste.com",
    "id": 3
  }
}
```

### Products

==========================

`GET /products`

Endpoint utilizada para acessar a listagem produtos disponiveis.

`GET /products - STATUS 200`

```json
[
  {
    "name": "Hamburguer",
    "category": "Sanduíches",
    "price": 14,
    "id": 1,
    "img": "https://www.imagensempng.com.br/wp-content/uploads/2021/06/X-burguer-Png.png"
  },
  {
    "name": "X-burguer",
    "category": "Sanduíches",
    "price": 16,
    "id": 2,
    "img": "https://e7.pngegg.com/pngimages/612/278/png-clipart-hamburger-cheeseburger-french-fries-pizza-bob-s-pizza.png"
  },
  {
    "name": "Big Kenzie",
    "category": "Sanduíches",
    "price": 18,
    "id": 3,
    "img": "https://e7.pngegg.com/pngimages/936/187/png-clipart-hamburger-hamburger-food.png"
  },
  {
    "name": "Combo Kenzie",
    "category": "Combos",
    "price": 26,
    "id": 4,
    "img": "https://w7.pngwing.com/pngs/765/174/png-transparent-hamburger-veggie-burger-chicken-sandwich-kfc-french-fries-burger-king-food-recipe-fast-food-restaurant.png"
  },
  {
    "name": "Fanta Guarana",
    "category": "Bebidas",
    "price": 5,
    "id": 5,
    "img": "https://i.pinimg.com/originals/19/4b/27/194b275d22c5444d679861ec1beeeb1c.png"
  },
  {
    "name": "Coca-cola",
    "category": "Bebidas",
    "price": 7,
    "id": 6,
    "img": "https://www.designi.com.br/images/preview/10025261.jpg"
  },
  {
    "name": "Milkshake Ovomaltine",
    "category": "Sobremesas",
    "price": 10,
    "id": 7,
    "img": "https://w7.pngwing.com/pngs/59/617/png-transparent-milkshake-drink-takeout-tea-thumbnail.png"
  },
  {
    "name": "Sundae",
    "category": "Sobremesas",
    "price": 10,
    "id": 8,
    "img": "https://w7.pngwing.com/pngs/670/980/png-transparent-chocolate-ice-cream-ice-cream-cones-milkshake-sundae-ovaltine-sundae-food-frozen-dessert-parfait.png"
  }
]
```

### Cart

==========================

`POST /cart`

Conseguimos realizar a adição de produtos selecionados pelo usuário no carrinho com esse endpoint. É necessário o envio do id do usuário para que a requisição seja aceita.

```json
{
  "name": "Big Kenzie",
  "category": "Sanduíches",
  "price": 18,
  "userId": 3
}
```

É necessário o envio do token no cabeçalho da requisição, dessa forma:

> Authorization: Bearer {token}

`get /cart`

Com esse endpoint podemos verificar todos os livros já lidos pelos usuários.

`get /cart - STATUS 200`

```json
[
  {
    "name": "Big Kenzie",
    "category": "Sanduíches",
    "price": 18,
    "userId": 3,
    "id": 1
  }
]
```
