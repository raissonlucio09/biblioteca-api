# API REST de Biblioteca

Este projeto implementa uma API REST para gerenciamento de livros, utilizando Spring Boot, Spring Data JPA e H2 Database (em memória).

## Funcionalidades

- **CRUD Completo de Livros**: Permite criar, ler, atualizar e deletar informações de livros.
- **Validação de Dados**: Validação de campos como título, autor, ISBN e ano de publicação.
- **Banco de Dados H2**: Utiliza um banco de dados em memória H2 para facilitar o desenvolvimento e testes.
- **Padrão MVC**: Organização do código em Model, View (implícito na API REST), Controller e Service.

## Tecnologias Utilizadas

- Java 11
- Spring Boot 2.7.18
- Spring Web
- Spring Data JPA
- H2 Database
- Maven

## Como Executar o Projeto

1.  **Pré-requisitos**:
    - Java Development Kit (JDK) 11 ou superior.
    - Maven (gerenciador de dependências).

2.  **Clonar o repositório**:
    ```bash
    git clone <URL_DO_REPOSITORIO>
    cd biblioteca-api
    ```

3.  **Compilar e Executar**:
    ```bash
    ./mvnw clean install
    java -jar target/biblioteca-api-0.0.1-SNAPSHOT.jar
    ```

    A aplicação será iniciada na porta `8080`.

## Endpoints da API

A API estará disponível em `http://localhost:8080/api/livros`.

| Método HTTP | Endpoint           | Descrição                               |
| :---------- | :----------------- | :-------------------------------------- |
| `GET`       | `/api/livros`      | Lista todos os livros                   |
| `GET`       | `/api/livros/{id}` | Busca um livro pelo ID                  |
| `POST`      | `/api/livros`      | Adiciona um novo livro                  |
| `PUT`       | `/api/livros/{id}` | Atualiza um livro existente             |
| `DELETE`    | `/api/livros/{id}` | Deleta um livro pelo ID                 |

### Exemplo de Requisições (usando `curl`)

**Adicionar um livro (POST)**:

```bash
curl -X POST -H "Content-Type: application/json" -d '{"titulo": "O Senhor dos Anéis", "autor": "J.R.R. Tolkien", "isbn": "978-85-336-0314-9", "anoPublicacao": 1954}' http://localhost:8080/api/livros
```

**Listar todos os livros (GET)**:

```bash
curl -X GET http://localhost:8080/api/livros
```

**Buscar um livro por ID (GET)**:

```bash
curl -X GET http://localhost:8080/api/livros/1
```

**Atualizar um livro (PUT)**:

```bash
curl -X PUT -H "Content-Type: application/json" -d '{"titulo": "O Senhor dos Anéis - Edição Especial", "autor": "J.R.R. Tolkien", "isbn": "978-85-336-0314-9", "anoPublicacao": 2001}' http://localhost:8080/api/livros/1
```

**Deletar um livro (DELETE)**:

```bash
curl -X DELETE http://localhost:8080/api/livros/1
```

## Console H2

O console do banco de dados H2 pode ser acessado em `http://localhost:8080/h2-console` após iniciar a aplicação. Utilize as seguintes credenciais:

- **JDBC URL**: `jdbc:h2:mem:bibliotecadb`
- **User Name**: `sa`
- **Password**: (deixe em branco)


