# Desafio Engineer Fullstack

## Descrição
Você foi contratado por uma startup de livraria online que precisa de um Catálogo de Livros. O sistema deve permitir que o time interno gerencie o estoque e que usuários finais pesquisem e visualizem informações dos livros.
O candidato deverá implementar um **Catálogo de Livros** com backend em Java/Spring Boot, frontend em ReactJS e dockerização completa.

## Tecnologias
- Java 17+ e Spring Boot
- Spring Data JPA  
- Banco de dados relacional (PostgreSQL ou MySQL)  
- ReactJS  
- Docker e/ou Docker Compose  
- Git

## Backend (Spring Boot):
	-	CRUD de livros: título, autor, ISBN, data de publicação, quantidade em estoque, preço.
	-	Busca paginada e filtrada por título e autor.
	-	Endpoints REST seguindo boas práticas (status HTTP adequados, DTOs, tratamento de exceções).

## Frontend (ReactJS):
	-	Listagem paginada de livros com filtros por título/autor.
	-	Formulário para criar e editar livros (validar campos obrigatórios).
	-	Tela de detalhe do livro.
	-	Navegação entre rotas (React Router ou similar).

## Docker:
	-	Dockerfile para o backend e outro para o frontend.
	-	Compor ambos em um docker-compose.yml, incluindo um container de banco (PostgreSQL ou MySQL).

## Pré-requisitos
- Java 17 ou superior  
- Node.js 14 ou superior  
- Docker e Docker Compose  
- Git  

## Estrutura do Projeto
```
.
├── backend/            # API em Spring Boot
├── frontend/           # Aplicação ReactJS
├── docker-compose.yml  # Composição dos containers
└── README.md           # Documentação básica do projeto
```

## Endpoints Principais (exemplos)
- `GET /api/livros?page=0&size=10&titulo=&autor=`  
- `POST /api/livros`  
  ```json
  {
    "titulo": "Título Exemplo",
    "autor": "Autor Exemplo",
    "isbn": "123-4567890123",
    "dataPublicacao": "2025-01-01",
    "quantidade": 100,
    "preco": 59.90
  }
  ```
- `PUT /api/livros/{id}`  
- `DELETE /api/livros/{id}`  
- `GET /api/livros/{id}`  

## Critérios de Avaliação
- Arquitetura e boas práticas  
- Qualidade de código e padrões  
- Funcionalidade completa  
- Testes unitários/integrados (bônus)  
- Dockerização e scripts  
- Documentação clara
