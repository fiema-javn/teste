

1. Visão Geral

Você deverá criar uma aplicação Spring Boot que gerencie um carrinho de compras simples, com persitência em PostgreSQL e execução via Docker Compose. Todo o código deve estar em um repositório Git (GitHub, GitLab ou similar), com histórico de commits claros e um README orientando a execução.


2. Pré-requisitos
	•	Java 17 ou superior
	•	Maven ou Gradle
	•	Docker e Docker Compose
	•	Conta em plataforma Git (GitHub, GitLab etc.)
	•	IDE de sua preferência (IntelliJ IDEA, VS Code, Eclipse)


3. Estrutura do Repositório

cart-app/
├── src/
│   ├── main/
│   │   ├── java/com/candidato/cart
│   │   │   ├── controller/
│   │   │   ├── model/
│   │   │   ├── repository/
│   │   │   └── service/
│   │   └── resources/
│   │       ├── application.yml
│   │       └── data.sql    (opcional, para dados iniciais de produtos)
│   └── test/
│       └── java/com/candidato/cart
└── .gitignore

4. Passo a Passo

4.1. Inicializar o Projeto
	1.	Crie o repositório e faça o primeiro commit com o README.md vazio.
	2.	No README, detalhe o objetivo (“Gerenciar carrinho de compras com Spring Boot e PostgreSQL via Docker Compose”).

4.2. Gere o Projeto Spring Boot
	1.	Use o Spring Initializr com no mínimo:
	•	Language: Java
	•	Packaging: Jar
	•	Dependencies:
	•	Spring Web
	•	Spring Data JPA
	•	PostgreSQL Driver
	2.	Importe o projeto na sua IDE.
	3. Se necessário, adicione outras bibliotecas.

4.3. Definir o Modelo de Dados
	•	Product
	•	id: Long (PK)
	•	name: String
	•	price: BigDecimal
	•	CartItem
	•	id: Long (PK)
	•	product: Product (ManyToOne)
	•	quantity: int
	•	Cart
	•	id: Long (PK)
	•	items: List<CartItem> (OneToMany, cascade ALL)

4.4. Configurar Banco de Dados

Em src/main/resources/application.yml:

spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/cartdb
    username: cartuser
    password: cartpass
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true

4.5. Criar Docker Compose

No arquivo docker-compose.yml na raiz:

version: '3.8'
services:
  db:
    image: postgres:15
    environment:
      POSTGRES_DB: cartdb
      POSTGRES_USER: cartuser
      POSTGRES_PASSWORD: cartpass
    ports:
      - "5432:5432"
    volumes:
      - db_data:/var/lib/postgresql/data
volumes:
  db_data:

→ Instrução de uso:

docker-compose up -d

4.6. Repositórios e Serviços
	1.	Em repository/, crie interfaces que estendam JpaRepository para Product, CartItem e Cart.
	2.	Em service/CartService:
	•	createCart(): inicializa e salva novo Cart
	•	addItem(cartId, productId, quantity): busca entidades, adiciona/atualiza CartItem, salva Cart
	•	removeItem(cartId, itemId): remove CartItem e salva Cart

4.7. Controladores REST

Em controller/CartController, implemente endpoints:
	•	POST /carts → cria novo carrinho
	•	POST /carts/{cartId}/items
{ "productId": 1, "quantity": 2 }
adiciona item

	•	DELETE /carts/{cartId}/items/{itemId} → remove item
	•	GET /carts/{cartId} → retorna estado atual do carrinho

4.8. Dados Iniciais de Produtos (Opcional)

Em src/main/resources/data.sql:

INSERT INTO product (id, name, price) VALUES (1, 'Caneca', 19.90);
INSERT INTO product (id, name, price) VALUES (2, 'Camiseta', 49.90);

4.9. Testes Automatizados
	•	Teste Unitário: (JUnit 5 + Mockito) para métodos de CartService.
⸻

5. Entrega Final
	1.	Clonar o repositório.
	2.	Subir o banco: docker-compose up -d.
	3.	Rodar a aplicação:
	4. 	Enviar uma request via curl, Postman ou Insomnia para testar os endpoints.

⸻
