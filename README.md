# Desafio Estagiário Fullstack

## Descrição
Este repositório contém o desafio técnico para vaga de Desenvolvedor Fullstack Júnior. O candidato deverá implementar uma **Lista de Desejos de Livros** com backend em Java/Spring Boot e frontend em ReactJS.

## Tecnologias
- Java 17+ e Spring Boot  
- Spring Web e Spring Data JPA (H2)  
- ReactJS  
- Git  

## Pré-requisitos
- Java 17 ou superior  
- Node.js 14 ou superior  
- Git  

## Estrutura do Projeto
```
.
├── backend/            # API em Spring Boot + H2
├── frontend/           # Aplicação ReactJS
└── README_JUNIOR.md    # Este arquivo
```

## Setup e Execução

## Endpoints
- `GET /wishlists/{usuarioId}`  
- `POST /wishlists`  
  ```json
  {
    "usuarioId": "seu-uuid",
    "titulo": "Título Exemplo",
    "autor": "Autor Exemplo"
  }
  ```

## Critérios de Avaliação
- Funcionalidade mínima  
- Clareza e organização do código  
- Integração Front–Back  
- Documentação básica
