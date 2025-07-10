# Desafio Engineer Fullstack

## Descrição
Este repositório contém o desafio técnico para vaga de Desenvolvedor Fullstack. O candidato deverá implementar um **Catálogo de Livros** com backend em Java/Spring Boot, frontend em ReactJS e dockerização completa.

## Tecnologias
- Java 17+ e Spring Boot  
- Spring Data JPA  
- Banco de dados relacional (PostgreSQL ou MySQL)  
- ReactJS  
- Docker e Docker Compose  
- Git  

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
└── README_PLENO.md     # Este arquivo
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
