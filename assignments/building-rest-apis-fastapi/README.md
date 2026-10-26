# 📘 Assignment: Building REST APIs with FastAPI

## 🎯 Objective

Construa uma API REST para um catálogo de livros usando FastAPI. Você praticará rotas HTTP, modelos de dados, operações CRUD e validação de requisições.

## 📝 Tasks

### 🛠️ Create the FastAPI App and List Books

#### Descrição
Crie uma aplicação FastAPI para um catálogo de livros e implemente endpoints para verificar se a API está funcionando e listar os livros disponíveis.

#### Requisitos
A aplicação concluída deve:

- Criar uma instância `FastAPI` em `main.py`
- Implementar `GET /` ou `GET /health` que retorne uma mensagem indicando que a API está funcionando
- Implementar `GET /books` que retorne uma lista de livros, inicialmente vazia ou com pelo menos dois exemplos
- Iniciar com `uvicorn main:app --reload` e permitir acesso à documentação interativa em `/docs`


### 🛠️ Add Book Models and Create and Retrieve Endpoints

#### Descrição
Defina a estrutura de um livro e adicione endpoints para criar um livro e consultar um livro pelo seu identificador.

#### Requisitos
A aplicação concluída deve:

- Definir um modelo Pydantic `Book` com `id`, `title`, `author` e `published_year`
- Implementar `POST /books` para criar um livro e retornar o livro criado com status HTTP `201`
- Implementar `GET /books/{book_id}` para retornar o livro com o identificador solicitado
- Armazenar os livros em memória e retornar status HTTP `404` quando o identificador não existir

Exemplo de corpo para `POST /books`:

```json
{
  "id": 1,
  "title": "The Hobbit",
  "author": "J. R. R. Tolkien",
  "published_year": 1937
}
```


### 🛠️ Complete CRUD and Validate the API

#### Descrição
Complete as operações de atualização e remoção para que os usuários possam gerenciar o catálogo pela API.

#### Requisitos
A aplicação concluída deve:

- Implementar `PUT /books/{book_id}` para atualizar os dados de um livro existente
- Implementar `DELETE /books/{book_id}` para remover um livro existente
- Retornar status HTTP `404` ao tentar atualizar, consultar ou remover um livro inexistente
- Usar a validação de dados do Pydantic para rejeitar campos ausentes ou valores com tipos incorretos
- Testar o fluxo de criar, consultar, atualizar e remover livros usando `/docs` ou um cliente HTTP
