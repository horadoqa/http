# Métodos HTTP

Os **métodos HTTP** (também chamados de *HTTP verbs*) definem a ação que um cliente (como um navegador ou aplicativo) deseja realizar em um recurso de um servidor. Eles são fundamentais para a comunicação na Web e em APIs REST.

### 1. GET

**Função:** Recuperar informações de um recurso.

* Não deve alterar dados no servidor.
* Pode ser armazenado em cache.
* Os parâmetros geralmente são enviados na URL.

**Exemplo:**

```http
GET /usuarios/123
```

**Uso:** Buscar dados de um usuário.

---

### 2. POST

**Função:** Criar um novo recurso ou enviar dados para processamento.

* Envia dados no corpo da requisição.
* Pode modificar o estado do servidor.

**Exemplo:**

```http
POST /usuarios
Content-Type: application/json

{
  "nome": "João",
  "email": "joao@email.com"
}
```

**Uso:** Cadastrar um novo usuário.

---

### 3. PUT

**Função:** Atualizar completamente um recurso existente.

* Normalmente substitui todos os dados do recurso.
* É considerado idempotente (múltiplas requisições produzem o mesmo resultado).

**Exemplo:**

```http
PUT /usuarios/123
Content-Type: application/json

{
  "nome": "João Silva",
  "email": "joao@email.com"
}
```

**Uso:** Atualizar todos os dados de um usuário.

---

### 4. PATCH

**Função:** Atualizar parcialmente um recurso.

* Modifica apenas os campos informados.
* Mais eficiente quando poucas informações precisam ser alteradas.

**Exemplo:**

```http
PATCH /usuarios/123
Content-Type: application/json

{
  "email": "novoemail@email.com"
}
```

**Uso:** Alterar apenas o e-mail de um usuário.

---

### 5. DELETE

**Função:** Remover um recurso.

* Pode excluir permanentemente ou marcar para exclusão, dependendo da implementação.

**Exemplo:**

```http
DELETE /usuarios/123
```

**Uso:** Excluir um usuário.

---

### 6. HEAD

**Função:** Obter apenas os cabeçalhos da resposta.

* Sem retornar o corpo do conteúdo.
* Útil para verificar existência, tamanho ou data de modificação de um recurso.

**Exemplo:**

```http
HEAD /arquivo.pdf
```

**Uso:** Verificar informações sobre um arquivo antes de baixá-lo.

---

### 7. OPTIONS

**Função:** Descobrir quais métodos são suportados por um recurso.

* Muito utilizado em requisições CORS (*Cross-Origin Resource Sharing*).

**Exemplo:**

```http
OPTIONS /usuarios
```

**Resposta possível:**

```http
Allow: GET, POST, PUT, DELETE
```

---

### 8. TRACE

**Função:** Realizar um diagnóstico do caminho percorrido pela requisição.

* Pouco utilizado atualmente.
* Frequentemente desabilitado por questões de segurança.

---

### 9. CONNECT

**Função:** Estabelecer um túnel de comunicação com o servidor.

* Utilizado principalmente por proxies para conexões HTTPS.

**Exemplo:**

```http
CONNECT exemplo.com:443
```

---

## Tabela Resumo

| Método  | Objetivo                      | Altera Dados?   | Idempotente? |
| ------- | ----------------------------- | --------------- | ------------ |
| GET     | Consultar recurso             | Não             | Sim          |
| POST    | Criar recurso                 | Sim             | Não          |
| PUT     | Atualizar completamente       | Sim             | Sim          |
| PATCH   | Atualizar parcialmente        | Sim             | Depende      |
| DELETE  | Remover recurso               | Sim             | Sim          |
| HEAD    | Obter cabeçalhos              | Não             | Sim          |
| OPTIONS | Consultar métodos disponíveis | Não             | Sim          |
| TRACE   | Diagnóstico                   | Não             | Sim          |
| CONNECT | Criar túnel de comunicação    | Não diretamente | Não          |

## Exemplo em uma API REST

Imagine uma API de produtos:

```http
GET    /produtos        -> Listar produtos
GET    /produtos/10     -> Buscar produto 10
POST   /produtos        -> Criar produto
PUT    /produtos/10     -> Atualizar produto inteiro
PATCH  /produtos/10     -> Atualizar parte do produto
DELETE /produtos/10     -> Excluir produto
```

Essa convenção torna as APIs mais intuitivas, padronizadas e fáceis de manter.

