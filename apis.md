# APIs que podem ser utilizadas com os Methodos HTTP.

Praticamente toda API web moderna utiliza métodos HTTP. Abaixo estão alguns exemplos populares e como os métodos são aplicados.

## 1. [GitHub REST API](https://docs.github.com/en/rest?utm_source=chatgpt.com)

Permite gerenciar repositórios, usuários, issues e pull requests.

**Exemplos:**

```http
GET /users/octocat
```

Busca informações de um usuário.

```http
POST /user/repos
```

Cria um novo repositório.

```http
PATCH /repos/usuario/projeto
```

Atualiza informações de um repositório.

```http
DELETE /repos/usuario/projeto
```

Remove um repositório.

---

## 2. [JSONPlaceholder](https://jsonplaceholder.typicode.com?utm_source=chatgpt.com)

API gratuita para testes e aprendizado.

**Exemplos:**

```http
GET /posts
```

Lista posts.

```http
POST /posts
```

Cria um post.

```http
PUT /posts/1
```

Atualiza completamente o post 1.

```http
PATCH /posts/1
```

Atualiza parcialmente o post 1.

```http
DELETE /posts/1
```

Remove o post 1.

---

## 3. [OpenWeather API](https://openweathermap.org/api?utm_source=chatgpt.com)

Fornece dados meteorológicos.

**Exemplo:**

```http
GET /data/2.5/weather?q=Rio%20de%20Janeiro
```

Obtém a previsão do tempo para uma cidade.

Nesse caso, a API utiliza principalmente o método **GET**, pois o objetivo é consultar dados.

---

## 4. [Stripe API](https://stripe.com/docs/api?utm_source=chatgpt.com)

Utilizada para pagamentos online.

**Exemplos:**

```http
POST /v1/customers
```

Cria um cliente.

```http
GET /v1/customers/cus_123
```

Consulta um cliente.

```http
POST /v1/payment_intents
```

Cria uma intenção de pagamento.

```http
DELETE /v1/customers/cus_123
```

Remove um cliente.

---

## 5. [X API (Twitter API)](https://developer.x.com/en/docs?utm_source=chatgpt.com)

Permite publicar e consultar tweets.

**Exemplos:**

```http
GET /2/tweets
```

Busca tweets.

```http
POST /2/tweets
```

Publica um novo tweet.

```http
DELETE /2/tweets/{id}
```

Exclui um tweet.

---

## 6. [ViaCEP](https://viacep.com.br?utm_source=chatgpt.com)

API brasileira para consulta de CEPs.

**Exemplo:**

```http
GET /ws/01001000/json
```

Retorna endereço correspondente ao CEP informado.

---

## 7. [PokéAPI](https://pokeapi.co?utm_source=chatgpt.com)

API pública sobre Pokémon.

**Exemplo:**

```http
GET /api/v2/pokemon/pikachu
```

Retorna informações do Pikachu.

---

## Exemplo prático de CRUD com HTTP

Imagine uma API de usuários:

| Operação               | Método HTTP | Endpoint      |
| ---------------------- | ----------- | ------------- |
| Listar usuários        | GET         | `/usuarios`   |
| Buscar usuário         | GET         | `/usuarios/1` |
| Criar usuário          | POST        | `/usuarios`   |
| Atualizar usuário      | PUT         | `/usuarios/1` |
| Atualizar parcialmente | PATCH       | `/usuarios/1` |
| Excluir usuário        | DELETE      | `/usuarios/1` |

Essa combinação de **métodos HTTP + endpoints** forma a base da maioria das APIs REST utilizadas em aplicações web, mobile e sistemas corporativos.
