# 📘 Assignment: Automated Testing for FastAPI

## 🎯 Objective

Escreva testes automatizados para uma API de catálogo de livros criada com FastAPI. Você aprenderá a usar `pytest` e `TestClient` para verificar respostas, operações CRUD e casos de erro sem iniciar um servidor.

## 📝 Tasks

### 🛠️ Set Up the Test Client

#### Descrição
Continue o projeto da assignment Building REST APIs with FastAPI. Configure um cliente de testes para enviar requisições diretamente à aplicação e escreva os primeiros testes.

#### Requisitos
Os testes concluídos devem:

- Instalar as dependências necessárias com `pip install pytest httpx`
- Criar `test_main.py` e importar a aplicação FastAPI do módulo `main`
- Criar um `TestClient` para a aplicação
- Verificar que `GET /` ou `GET /health` retorna status HTTP `200`
- Verificar que `GET /books` retorna status HTTP `200` e uma lista JSON


### 🛠️ Test Book CRUD Operations

#### Descrição
Adicione testes para verificar que os endpoints de livros criam, consultam, atualizam e removem dados corretamente.

#### Requisitos
Os testes concluídos devem:

- Verificar que `POST /books` cria um livro e retorna status HTTP `201` com os dados esperados
- Verificar que `GET /books/{book_id}` retorna o livro criado com status HTTP `200`
- Verificar que `PUT /books/{book_id}` atualiza o livro e retorna status HTTP `200` com os dados atualizados
- Verificar que `DELETE /books/{book_id}` remove o livro e retorna status HTTP `204`
- Executar `pytest -v` e confirmar que os testes passam


### 🛠️ Test Errors and Invalid Data

#### Descrição
Garanta que a API responda corretamente a requisições que não podem ser atendidas, como procurar um livro inexistente ou enviar dados inválidos.

#### Requisitos
Os testes concluídos devem:

- Verificar que consultar, atualizar ou remover um livro inexistente retorna status HTTP `404`
- Verificar que enviar campos obrigatórios ausentes ou tipos incorretos para `POST /books` retorna status HTTP `422`
- Usar dados de teste que não dependam de uma ordem específica de execução
- Confirmar que `pytest -v` executa toda a suíte sem deixar dados de um teste interferirem em outro
