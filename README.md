# 📚 Bookstore E-Commerce — Microservices Architecture

A full-stack **Bookstore E-Commerce** platform built using **Spring Boot 3.x** and **Spring Cloud** following a **Microservices Architecture**.

Each service is independently deployable, owns its own database, and communicates using **REST APIs (Feign Client)** and **Apache Kafka Events**.

---

# 🏗️ Architecture Overview

```text
Client → API Gateway (8080)
           ↓
    ┌──────────────────────────────────────────┐
    │        Spring Cloud Eureka Server        │
    │          Service Discovery (8761)        │
    └──────────────────────────────────────────┘
           ↓

┌─────────────────────────────────────────────────────────────┐
│ User │ Product │ Cart │ Wishlist │ Order │ Feedback │ Admin │
│ 8081 │  8083   │ 8084 │   8085   │ 8087  │   8088   │ 8082  │
└─────────────────────────────────────────────────────────────┘
           ↓

    ┌──────────────────────────────────────────┐
    │            Apache Kafka Bus              │
    │      order-events / user-events          │
    └──────────────────────────────────────────┘
           ↓

    ┌──────────────────────────────────────────┐
    │         Notification Service (8089)      │
    └──────────────────────────────────────────┘
```

---

# 🧩 Microservices

| Service | Port | Description |
|----------|------|-------------|
| User Service | 8081 | Authentication, JWT, user management |
| Admin Service | 8082 | Admin operations and product management |
| Product Service | 8083 | Product & category CRUD |
| Cart Service | 8084 | Shopping cart management |
| Wishlist Service | 8085 | Wishlist management |
| Customer Service | 8086 | Customer details & addresses |
| Order Service | 8087 | Order lifecycle management |
| Feedback Service | 8088 | Product reviews & ratings |
| Notification Service | 8089 | Kafka-based notifications |
| Eureka Server | 8761 | Service discovery |
| Config Server | 8888 | Centralized configuration |
| API Gateway | 8080 | API routing & security |
| Common Lib | — | Shared DTOs, utilities & exceptions |

---

# 🔐 Security

- JWT-based Authentication
- Spring Security
- Role-based Authorization
    - USER
    - ADMIN
    - SUPER_ADMIN
- Stateless Architecture
- JWT validation at API Gateway

---

# 🛠️ Tech Stack

| Component | Technology |
|------------|------------|
| Language | Java 17 |
| Framework | Spring Boot 3.x |
| Service Discovery | Netflix Eureka |
| API Gateway | Spring Cloud Gateway |
| Config Server | Spring Cloud Config |
| Security | Spring Security + JWT |
| Messaging | Apache Kafka |
| Database | MySQL 8 |
| Cache | Redis |
| Inter-Service Communication | OpenFeign |
| Documentation | Swagger / OpenAPI |
| Build Tool | Maven |
| Containerization | Docker |

---

# 🚀 Running the Project

## 📋 Prerequisites

- Java 17+
- Maven 3.8+
- MySQL 8+
- Redis
- Docker
- Git

---

# ▶️ Start Services Order

```text
1. Eureka Server
2. Config Server
3. API Gateway
4. User Service
5. Admin Service
6. Product Service
7. Cart Service
8. Wishlist Service
9. Customer Service
10. Order Service
11. Feedback Service
12. Notification Service
```

---

# 🗄️ Create Databases

```sql
CREATE DATABASE bookstore_user;
CREATE DATABASE bookstore_admin;
CREATE DATABASE bookstore_product;
CREATE DATABASE bookstore_wishlist;
CREATE DATABASE bookstore_customer;
CREATE DATABASE bookstore_order;
CREATE DATABASE bookstore_feedback;
```

---

# 📡 Swagger UI

```text
http://localhost:{PORT}/swagger-ui.html
```

### Example

```text
http://localhost:8081/swagger-ui.html
```

---

# 📁 Project Structure

```text
bookstore-microservices/
│
├── eureka-server/
├── config-server/
├── api-gateway/
├── common-lib/
│
├── user-service/
├── admin-service/
├── product-service/
├── cart-service/
├── wishlist-service/
├── customer-service/
├── order-service/
├── feedback-service/
├── notification-service/
│
└── docker-compose.yml
```

---

# 🌿 Git Flow Strategy

```text
main        → Production branch
develop     → Integration branch
feature/*   → Individual feature branches
```

### Examples

```text
feature/user-service
feature/product-service
feature/cart-service
feature/order-service
feature/api-gateway
feature/config-server
```

---

# 📌 Features

- Microservices Architecture
- API Gateway Routing
- Eureka Service Discovery
- Centralized Config Server
- JWT Authentication
- Kafka Event-Driven Communication
- Redis Cart Management
- Swagger API Documentation
- Docker Support
- Role-Based Authorization

---
