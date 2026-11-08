# fastapi-learning-lab
Learning lab for front connection to backend and communications of them
# FastAPI PostgreSQL Authentication & CRUD Application

A full-stack backend application built using **FastAPI, PostgreSQL, SQLAlchemy, and JWT Authentication**. This project focuses on REST API development, database integration, user authentication, and API security.

## 🚀 Project Overview

This project demonstrates how to build a backend application using FastAPI, integrate PostgreSQL with SQLAlchemy, perform CRUD operations, and implement secure user authentication using JWT.

It also explores OAuth2, authentication vs authorization, and role-based access control (RBAC).

## 🛠️ Tech Stack

- **Backend:** FastAPI
- **Programming Language:** Python
- **Database:** PostgreSQL
- **ORM:** SQLAlchemy
- **Data Validation:** Pydantic
- **Authentication:** JWT (JSON Web Tokens)
- **Password Hashing:** Argon2
- **API Documentation:** Swagger UI
- **Server:** Uvicorn
- **Frontend Integration:** React / REST API

## 📌 Features & Learning Objectives

### 1. FastAPI Fundamentals

- Building a server using FastAPI.
- Creating REST API endpoints.
- Understanding HTTP methods:
  - GET
  - POST
  - PUT
  - PATCH
  - DELETE
- Fetching all products and retrieving products by ID.
- Understanding API request and response handling.

### 2. Pydantic Data Validation

- Using Pydantic models for request validation.
- Defining request and response schemas.
- Validating incoming JSON data.
- Using response models to structure API responses.

### 3. Database Integration with SQLAlchemy

- Integrating PostgreSQL with FastAPI.
- Connecting databases using SQLAlchemy.
- Understanding database engines and sessions.
- Creating database models and tables.
- Implementing database dependencies using `Depends()`.
- Performing database operations.

### 4. CRUD Operations

- Creating new products.
- Fetching all products.
- Fetching individual products by ID.
- Updating existing products.
- Partially updating product information.
- Deleting products.
- Managing database transactions using SQLAlchemy.

### 5. Authentication & Authorization

Understanding the difference between authentication and authorization.

| Authentication | Authorization |
|---|---|
| Verifies who the user is | Determines what the user can access |
| Checks user credentials | Checks user permissions |
| Happens during login | Happens when accessing protected resources |

### 6. JWT-Based Authentication

- Understanding JSON Web Tokens (JWT).
- User registration and login.
- Secure password hashing using Argon2.
- Password verification.
- Generating JWT access tokens.
- Understanding JWT payloads, signatures, and expiration.
- Verifying JWT tokens.

### 7. OAuth2 with FastAPI

- Understanding OAuth2 password flow.
- Using `OAuth2PasswordRequestForm`.
- Implementing `OAuth2PasswordBearer`.
- Extracting Bearer tokens.
- Understanding token-based authentication.
- Integrating OAuth2 dependencies with FastAPI.

### 8. Securing APIs

- Protecting API endpoints.
- Using FastAPI dependency injection.
- Implementing `get_current_user`.
- Validating authenticated users.
- Restricting unauthorized access.
- Understanding API security best practices.

### 9. Role-Based Access Control (RBAC)

- Understanding Role-Based Access Control.
- Managing user roles and permissions.
- Restricting endpoints based on user roles.
- Understanding admin and normal user permissions.

### 10. Full-Stack Integration

- Connecting frontend applications with FastAPI.
- Configuring CORS.
- Sending HTTP requests from the frontend.
- Integrating frontend forms with backend APIs.
- Handling API responses and errors.
- Understanding the frontend-to-backend communication flow.

## 📂 Project Structure

```text
fastapi-postgres-auth/
│
├── auth/
│   ├── __init__.py
│   ├── auth_models.py
│   ├── auth_schemas.py
│   ├── auth_utils.py
│   └── auth_main.py
│
├── main.py
├── database.py
├── models.py
├── schemas.py
│
├── requirements.txt
├── .env.example
├── .gitignore
└── README.md
```

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/fastapi-postgres-auth.git
```

```bash
cd fastapi-postgres-auth
```

### 2. Create a virtual environment

```bash
python -m venv fastapi-learn
```

Activate it on Windows:

```powershell
.\fastapi-learn\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure PostgreSQL

Create a PostgreSQL database:

```sql
CREATE DATABASE sree;
```

Configure your database connection using environment variables.

Example:

```env
DB_USER=postgres
DB_PASSWORD=your_password
DB_HOST=localhost
DB_PORT=5432
DB_NAME=sree
SECRET_KEY=your_secret_key
```

### 5. Run the application

```bash
uvicorn main:app --reload
```

### 6. Access API documentation

Open your browser:

- Swagger UI: http://127.0.0.1:8000/docs
- ReDoc: http://127.0.0.1:8000/redoc

## 🔗 API Endpoints

### Products API

| Method | Endpoint | Description |
|---|---|---|
| GET | `/products/` | Fetch all products |
| GET | `/products/{id}` | Fetch product by ID |
| POST | `/products/` | Create a product |
| PUT | `/products/{id}` | Update a product |
| PATCH | `/products/{id}` | Partially update a product |
| DELETE | `/products/{id}` | Delete a product |

### Authentication API

| Method | Endpoint | Description |
|---|---|---|
| POST | `/auth/register` | Register a new user |
| POST | `/auth/login` | Authenticate user and generate JWT |
| GET | `/auth/me` | Get current authenticated user |

## 🔐 Authentication Workflow

```text
              User Registration
                     |
                     v
               FastAPI Backend
                     |
                     v
             Validate User Details
                     |
                     v
              Hash Password
                 (Argon2)
                     |
                     v
              PostgreSQL DB
                     |
                     v
                User Login
                     |
                     v
             Verify Password
                     |
                     v
               Generate JWT
                     |
                     v
              Return Access Token
                     |
                     v
          Access Protected Endpoints
                     |
                     v
               Verify JWT
                     |
                     v
                API Access
```

## 🔒 API Security Best Practices

- Never store plain-text passwords.
- Use secure password hashing algorithms.
- Keep JWT secret keys in environment variables.
- Validate all incoming request data.
- Protect sensitive API endpoints.
- Use HTTPS in production.
- Implement appropriate token expiration.
- Apply role-based access restrictions where required.
- Never commit database credentials or secrets to GitHub.

## 🎯 Learning Outcomes

Through this project, I am developing practical knowledge of:

- REST API development using FastAPI.
- PostgreSQL database integration.
- SQLAlchemy ORM and database sessions.
- Pydantic data validation.
- CRUD application development.
- Authentication and authorization.
- JWT and OAuth2 concepts.
- Password hashing and API security.
- Full-stack application integration.

## 🚧 Future Enhancements

- Implement complete RBAC with admin and user roles.
- Add refresh token functionality.
- Add Alembic database migrations.
- Dockerize the application.
- Build CI/CD pipelines.
- Deploy the application on AWS.
- Add automated API testing.

---

**Learning by building.** This project is part of my journey to understand backend development, database management, authentication, and secure API development using Python and FastAPI.
