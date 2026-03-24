# 🏦 Loan Origination System

A full-stack enterprise-grade loan management platform with a **Maker-Checker approval workflow**, built with React and Spring Boot.

## 🎯 Features

- **3-Role System**: Customer, Maker (loan officer), Checker (approver)
- **Maker-Checker Workflow**: Dual-approval process for loan applications
- **JWT Authentication** with role-based access control
- **Loan Application Flow**: Submit → Maker Review → Checker Approval
- **Document Upload & Management**
- **Real-time Notifications**
- **Forgot/Reset Password** with security questions
- **Swagger API Documentation** at `/swagger-ui.html`
- **Eligibility Checker** for pre-application screening

## 🛠 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | React 18, React Router v7, Bootstrap 5, Axios |
| Backend | Java 17, Spring Boot 3.2, Spring Security |
| Database | PostgreSQL, Spring Data JPA |
| Auth | JWT (jjwt) |
| API Docs | SpringDoc OpenAPI / Swagger |

## 🏗 Architecture
```
Frontend (React)
    ↓ Axios HTTP
REST Controllers
    ↓
Services (Business Logic)
    ↓
Repositories (JPA)
    ↓
PostgreSQL
```

### Application Status Flow
```
CUSTOMER SUBMITS → WITH_MAKER
    ↓
MAKER REVIEWS
    ├── Approve → WITH_CHECKER
    └── Reject  → REJECTED
        ↓
CHECKER REVIEWS
    ├── Approve → APPROVED
    └── Reject  → REJECTED
```

## ⚙️ How to Run

### Backend
```bash
cd backend
# Configure PostgreSQL in application.properties
./mvnw spring-boot:run
# API runs at http://localhost:8080
# Swagger UI: http://localhost:8080/swagger-ui.html
```

### Frontend
```bash
cd frontend
npm install
npm start
# App runs at http://localhost:3000
```

## 📁 Project Structure
```
├── backend/          # Spring Boot application
│   └── src/main/java/
│       ├── controllers/   # REST endpoints
│       ├── services/      # Business logic
│       ├── entities/      # JPA models
│       ├── dto/           # Request/Response objects
│       └── config/        # Security & JWT config
└── frontend/         # React application
    └── src/
        ├── Public/        # Login, Signup, Home pages
        ├── Customer/      # Customer dashboard & forms
        ├── Maker/         # Loan officer views
        └── Checker/       # Checker approval views
```
