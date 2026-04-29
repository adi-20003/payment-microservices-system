# Payment Microservices System

A production-style backend project built with Java and Spring Boot to simulate real-world banking and payment workflows. It includes:

- **user-service** for registration, login, JWT authentication, and role-based access
- **payment-service** for creating and viewing payment records
- **standing-order-service** for managing recurring payment instructions
- **direct-debit-service** for mandate-based debit requests
- **api-gateway** for routing requests to downstream services

This project is intentionally aligned with payment-domain backend development and is suitable for showcasing on GitHub and in a Java developer resume.

## Tech Stack

- Java 17
- Spring Boot 3.5.0
- Spring Cloud Gateway
- Spring Security
- JWT (jjwt)
- Spring Data JPA
- H2 Database
- Maven multi-module project

## Service Ports

- API Gateway: **8080**
- User Service: **8081**
- Payment Service: **8082**
- Standing Order Service: **8083**
- Direct Debit Service: **8084**

## Architecture

```text
Client
  |
  v
API Gateway (8080)
  |----> User Service (8081)
  |----> Payment Service (8082)
  |----> Standing Order Service (8083)
  |----> Direct Debit Service (8084)
```

## Key Features

- Secure registration and login APIs
- JWT token generation and validation
- REST APIs for payment workflows
- Clean layered architecture: controller, service, repository, entity, dto
- Basic exception handling and validation
- Sample seed data and H2 console support

## Build and Run

### 1. Build all modules

```bash
mvn clean package
```

### 2. Start services in separate terminals

```bash
cd user-service && mvn spring-boot:run
cd payment-service && mvn spring-boot:run
cd standing-order-service && mvn spring-boot:run
cd direct-debit-service && mvn spring-boot:run
cd api-gateway && mvn spring-boot:run
```

### 3. Test through gateway

Examples:

- POST `http://localhost:8080/auth/register`
- POST `http://localhost:8080/auth/login`
- GET `http://localhost:8080/api/payments`
- POST `http://localhost:8080/api/payments`
- GET `http://localhost:8080/api/standing-orders`
- GET `http://localhost:8080/api/direct-debits`

## Sample Register Request

```json
{
  "name": "Aditi Garg",
  "email": "aditi@example.com",
  "password": "Password@123",
  "role": "USER"
}
```

## Sample Login Request

```json
{
  "email": "aditi@example.com",
  "password": "Password@123"
}
```

## Sample Payment Request

```json
{
  "debtorName": "Aditi Garg",
  "creditorName": "ABC Utilities",
  "amount": 2500.00,
  "currency": "INR",
  "paymentType": "IMMEDIATE",
  "reference": "Electricity Bill"
}
```

## Resume Description

You can add this project on your resume like this:

**Payment Microservices System | Java, Spring Boot, JWT, Spring Security, H2, API Gateway**
- Built a multi-module backend system simulating real-world payment workflows including payments, standing orders, and direct debits.
- Implemented secure authentication and authorization using Spring Security and JWT.
- Designed RESTful APIs and routed traffic through a Spring Cloud Gateway.
- Applied layered architecture, validation, exception handling, and database persistence with Spring Data JPA.

## GitHub Upload Steps

1. Create a new public repository in your GitHub account named `payment-microservices-system`.
2. Upload all files from this folder.
3. Copy the public repository URL.
4. Add that GitHub URL to your resume.

Example URL format:

```text
https://github.com/<your-username>/payment-microservices-system
```
