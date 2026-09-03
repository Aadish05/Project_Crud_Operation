# Project_Crud_Operation
# Product CRUD REST API

A production-oriented REST API for managing Products and Items,
built using Java 17, Spring Boot, Spring Data JPA and PostgreSQL.

## Technology Stack

- Java 17
- Spring Boot
- Spring Web
- Spring Data JPA
- Hibernate
- PostgreSQL
- Spring Security
- JWT
- Refresh Token
- Jakarta Validation
- JUnit 5
- Mockito
- H2
- OpenAPI / Swagger
- Docker
- Docker Compose

## Architecture

The application follows a layered architecture:

Client
  ↓
Controller
  ↓
Service
  ↓
Repository
  ↓
PostgreSQL

Security is implemented before the controller layer:

Client
  ↓
JWT Filter
  ↓
Security Context
  ↓
Controller
  ↓
Service
  ↓
Repository
  ↓
Database

## API Versioning

All APIs are exposed under:

/api/v1/

Example:

GET /api/v1/products

## Product APIs

GET /api/v1/products
GET /api/v1/products/{id}
POST /api/v1/products
PUT /api/v1/products/{id}
DELETE /api/v1/products/{id}
GET /api/v1/products/{id}/items

## Pagination

GET /api/v1/products?page=0&size=20

## Example Request

POST /api/v1/products

{
  "productName": "Laptop"
}

## Running Locally

Prerequisites:

- Java 17+
- Maven
- PostgreSQL

Run:

mvn clean install

mvn spring-boot:run

## Running with Docker

docker compose up --build

Application:

http://localhost:8080

Swagger:

http://localhost:8080/swagger-ui.html

## Running Tests

mvn test

Tests use H2 instead of PostgreSQL.

## Database

PostgreSQL is used in production/development.

H2 is used for integration tests.

## Error Response

{
  "timestamp": "2026-09-03T10:00:00Z",
  "status": 404,
  "error": "NOT_FOUND",
  "message": "Product not found"
}
