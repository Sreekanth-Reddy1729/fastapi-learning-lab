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

- ###Project Flow 

                   ┌──────────────────────────┐
                   │       END USERS          │
                   │ Browser / Mobile / React │
                   └────────────┬─────────────┘
                                |
                                v
                   ┌──────────────────────────┐
                   │       DNS - ROUTE 53     │
                   │                          │
                   │ Domain name resolution  │
                   │ www.myapp.com            │
                   │ api.myapp.com            │
                   └────────────┬─────────────┘
                                |
                                v
                   ┌──────────────────────────┐
                   │     CDN - CLOUDFRONT     │
                   │                          │
                   │ Global Edge Locations    │
                   │ Content Caching          │
                   │ Faster Content Delivery  │
                   └────────────┬─────────────┘
                                |
                                v
                   ┌──────────────────────────┐
                   │       AWS WAF            │
                   │                          │
                   │ SQL Injection Protection │
                   │ XSS Protection           │
                   │ IP Filtering             │
                   │ Rate Limiting Rules      │
                   └────────────┬─────────────┘
                                |
                +---------------+----------------+
                |                                |
                v                                v
       ┌──────────────────┐            ┌──────────────────┐
       │ FRONTEND DELIVERY│            │  BACKEND TRAFFIC │
       │                  │            │                  │
       │ Amazon S3        │            │ Application      │
       │ HTML / CSS / JS  │            │ Load Balancer    │
       │ React Build      │            │ (ALB)             │
       └────────┬─────────┘            └────────┬─────────┘
                |                               |
                v                               v
       ┌──────────────────┐            ┌──────────────────┐
       │  BROWSER RENDER  │            │  FASTAPI SERVICE │
       │                  │            │                  │
       │ Frontend Loaded  │            │ Uvicorn          │
       │                  │            │ FastAPI          │
       └────────┬─────────┘            │ Middleware       │
                |                      │ API Router       │
                | API Request          └────────┬─────────┘
                |                               |
                +------------------------------>|
                                                v
                                   ┌────────────────────────┐
                                   │ AUTHENTICATION LAYER   │
                                   │                        │
                                   │ Registration           │
                                   │ Login                  │
                                   │ Argon2 Password Verify │
                                   │ JWT Generation         │
                                   │ JWT Validation         │
                                   │ OAuth2 Bearer          │
                                   └────────────┬───────────┘
                                                |
                                                v
                                   ┌────────────────────────┐
                                   │ AUTHORIZATION LAYER    │
                                   │                        │
                                   │ User Identity          │
                                   │ Roles / Permissions    │
                                   │ Access Control         │
                                   └────────────┬───────────┘
                                                |
                                                v
                                   ┌────────────────────────┐
                                   │ APPLICATION LAYER      │
                                   │                        │
                                   │ Business Logic         │
                                   │ Product Service        │
                                   │ User Service           │
                                   │ Request Validation     │
                                   │ Pydantic Schemas       │
                                   └────────────┬───────────┘
                                                |
                                                v
                                   ┌────────────────────────┐
                                   │ DATA ACCESS LAYER      │
                                   │                        │
                                   │ SQLAlchemy ORM         │
                                   │ Database Session       │
                                   │ Connection Pool        │
                                   └────────────┬───────────┘
                                                |
                                                v
                                   ┌────────────────────────┐
                                   │    DATABASE LAYER      │
                                   │                        │
                                   │ PostgreSQL / AWS RDS   │
                                   │                        │
                                   │ Users Table            │
                                   │ Products Table         │
                                   └────────────────────────┘


                  CI/CD AND DEPLOYMENT PIPELINE
                  =============================

        Developer
            |
            v
        GitHub Repository
            |
            v
        GitHub Actions / Jenkins
            |
            v
        Build Application
            |
            v
        Run Unit Tests
            |
            v
        SonarQube Code Analysis
            |
            v
        Trivy Security Scan
            |
            v
        Docker Image Build
            |
            v
        Push Image to Amazon ECR
            |
            v
        Deploy to ECS / EKS / EC2
            |
            v
        Health Checks
            |
            v
        Load Balancer Sends Traffic
        to Healthy Instances


                  MONITORING AND OBSERVABILITY
                  ===========================

        Application + Infrastructure
                    |
          +---------+----------+
          |         |          |
          v         v          v
       Metrics     Logs      Traces
          |         |          |
          v         v          v
      Prometheus  CloudWatch  OpenTelemetry
          |         |          |
          v         v          v
        Grafana   Dashboards  Trace Backend
          |         |          |
          +---------+----------+
                    |
                    v
              ALERT MANAGER
                    |
                    v
             Developer / DevOps
```


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



###complete flow 
# FastAPI Authentication – Complete Developer Flow

## Technologies

- Client: Browser / React / Postman
- Backend: FastAPI
- Server: Uvicorn
- Validation: Pydantic
- Database: PostgreSQL
- ORM: SQLAlchemy
- Password Security: pwdlib + Argon2
- Authentication scheme: OAuth2 Bearer
- Token format: JWT
- JWT library: python-jose

---

## 2. Complete Registration Flow

```text
                    CLIENT
                      |
                      | 1. POST /auth/register
                      |
                      | JSON BODY:
                      | {
                      |   username: "gowtham",
                      |   email: "test@gmail.com",
                      |   password: "mypassword"
                      | }
                      |
                      v
                 UVICORN SERVER
                      |
                      | Receives HTTP request
                      v
                 FASTAPI APPLICATION
                      |
                      v
                 AUTH ROUTER
                      |
                      | Matches /auth/register
                      v
                 PYDANTIC VALIDATION
                      |
                      | UserCreate schema
                      |
                      | Checks required fields
                      | Checks data types
                      | Validates email
                      v
                 REGISTRATION ENDPOINT
                      |
                      v
                 DATABASE DEPENDENCY
                      |
                      | Depends(get_db)
                      v
                 SQLALCHEMY SESSION
                      |
                      v
                 CHECK EXISTING USER
                      |
                      | Query username/email
                      v
                 POSTGRESQL DATABASE
                      |
                      | User already exists?
                      |
                 +----+----+
                 |         |
                YES        NO
                 |         |
                 v         v
              HTTP 409   ARGON2 HASHING
                         |
                         | plain password
                         |       |
                         |       v
                         | Generate salt
                         |       |
                         |       v
                         | Generate password hash
                         v
                   USER SQLALCHEMY MODEL
                         |
                         | Create User object
                         v
                   DATABASE SESSION
                         |
                         | db.add(user)
                         | db.commit()
                         | db.refresh(user)
                         v
                   POSTGRESQL DATABASE
                         |
                         | Store user details
                         | Store password HASH
                         v
                   USER RESPONSE SCHEMA
                         |
                         | UserResponse
                         | Excludes password
                         v
                   JSON RESPONSE
                         |
                         v
                      CLIENT
```

Registration stores the user. It does not automatically generate a JWT in this project.

---

## 3. Complete Login and JWT Generation Flow

```text
                    CLIENT
                      |
                      | 2. POST /auth/login
                      |
                      | FORM DATA:
                      | username=gowtham
                      | password=mypassword
                      |
                      v
                 UVICORN SERVER
                      |
                      v
                 FASTAPI APPLICATION
                      |
                      v
                 AUTH ROUTER
                      |
                      | Matches /auth/login
                      v
                 OAuth2PasswordRequestForm
                      |
                      | Extracts username
                      | Extracts password
                      v
                 LOGIN ENDPOINT
                      |
                      v
                 SQLALCHEMY SESSION
                      |
                      | Query user by username
                      v
                 POSTGRESQL DATABASE
                      |
                      | Returns user record
                      | Including password hash
                      v
                 VERIFY PASSWORD
                      |
                      | verify_password()
                      v
                 ARGON2 VERIFICATION
                      |
                      | Compare entered password
                      | with stored password hash
                      |
                 +----+----+
                 |         |
              INVALID     VALID
                 |         |
                 v         v
              HTTP 401   CREATE JWT PAYLOAD
                            |
                            | sub = user ID
                            | exp = expiration time
                            v
                       JWT ENCODING
                       python-jose
                            |
                            | jwt.encode()
                            | SECRET_KEY
                            | HS256 algorithm
                            v
                       SIGNED JWT TOKEN
                            |
                            v
                       TOKEN RESPONSE
                            |
                            | access_token
                            | token_type = bearer
                            v
                          CLIENT
```

### What happens during JWT generation?

```text
       USER ID + EXPIRATION TIME
                  |
                  v
             JWT PAYLOAD
                  |
                  v
        JWT HEADER + PAYLOAD
                  |
                  v
          SECRET KEY + HS256
                  |
                  v
          DIGITAL SIGNATURE
                  |
                  v
          COMPLETE JWT TOKEN
```

Example response:

```json
{
  "access_token": "eyJhbGciOiJIUzI1NiIs...",
  "token_type": "bearer"
}
```

The client receives this token. It does not receive the secret key.

---

## 4. Complete Protected API Request Flow

This is where JWT validation actually takes place.

```text
                    CLIENT
                      |
                      | 3. GET /auth/me
                      |
                      | Authorization Header:
                      | Bearer <JWT_TOKEN>
                      |
                      v
                 UVICORN SERVER
                      |
                      v
                 FASTAPI APPLICATION
                      |
                      v
                 AUTHENTICATION DEPENDENCY
                      |
                      | Depends(get_current_user)
                      v
                 OAuth2PasswordBearer
                      |
                      | Reads Authorization header
                      | Extracts Bearer token
                      |
                      | IMPORTANT:
                      | Does NOT verify JWT
                      v
                 get_current_user()
                      |
                      v
                 JWT DECODE
                      |
                      | jwt.decode()
                      | SECRET_KEY
                      | ALGORITHM = HS256
                      v
                 JWT VALIDATION
                      |
                      | 1. Verify signature
                      | 2. Check expiration (exp)
                      | 3. Decode token claims
                      |
                 +----+----+
                 |         |
               INVALID    VALID
                 |         |
                 v         v
              HTTP 401   EXTRACT USER ID
                            |
                            | payload["sub"]
                            v
                       DATABASE QUERY
                            |
                            | Find user by ID
                            v
                       POSTGRESQL
                            |
                            | Return user record
                            v
                       CURRENT USER OBJECT
                            |
                            v
                       PROTECTED ENDPOINT
                            |
                            | GET /auth/me
                            v
                       USER RESPONSE SCHEMA
                            |
                            v
                       JSON RESPONSE
                            |
                            v
                          CLIENT
```

---

## 5. Where does each validation happen?

| Stage | Component | What it validates |
|---|---|---|
| Registration | Pydantic | Username, email, password fields and types |
| Registration | PostgreSQL query | Duplicate username/email |
| Registration | Argon2 | Generates password hash |
| Login | SQLAlchemy | Finds user by username |
| Login | Argon2 | Checks entered password against stored hash |
| JWT generation | python-jose | Signs the JWT using the secret key |
| Protected request | OAuth2PasswordBearer | Extracts Bearer token |
| Protected request | jwt.decode() | Verifies signature and expiration |
| Protected request | SQLAlchemy | Finds the user associated with token |
| Authorization | Role/permission dependency | Checks whether user can access a resource |

---

## 6. Complete file-to-file execution flow

```text
                         main.py
                            |
                            | include_router()
                            v
                       auth_main.py
                            |
              +-------------+-------------+
              |             |             |
              v             v             v
          REGISTER         LOGIN       GET /auth/me
              |             |             |
              v             v             v
       auth_schemas.py  auth_schemas.py  get_current_user()
              |             |             |
              v             v             v
       UserCreate       OAuth2 Form    auth_utils.py
              |             |             |
              v             v             v
       auth_models.py  auth_models.py   jwt.decode()
              |             |             |
              +-------------+-------------+
                            |
                            v
                        database.py
                            |
                            v
                       PostgreSQL
```

### Responsibility of each file

| File | What it does |
|---|---|
| `main.py` | Creates FastAPI application and registers router |
| `database.py` | Creates engine, session and `get_db()` |
| `auth_main.py` | Registration, login and protected endpoints |
| `auth_schemas.py` | Request and response validation |
| `auth_models.py` | User database table |
| `auth_utils.py` | Password hashing, verification and JWT functions |

---

## 7. Important OAuth2 and JWT differences

| OAuth2PasswordRequestForm | OAuth2PasswordBearer | JWT |
|---|---|---|
| Reads login credentials | Extracts Bearer token | Represents token data |
| Used during login | Used during protected requests | Generated after successful login |
| Does not hash password | Does not validate JWT signature | Signed and later verified |
| Supplies username/password | Supplies token string | Carries claims |

**Remember:**

- Registration = Create user.
- Login = Verify password.
- JWT generation = Create signed access token.
- OAuth2PasswordBearer = Extract token.
- jwt.decode() = Validate token.
- get_current_user() = Identify authenticated user.
- Authorization = Check user permissions.

---

## 8. Important production security considerations

- Use HTTPS.
- Store `SECRET_KEY` in environment variables or a secrets manager.
- Never store plain-text passwords.
- Never store passwords or secret keys in JWT payloads.
- Always issue an expiration claim.
- Use short-lived access tokens.
- Implement refresh-token handling if required.
- Use role-based authorization for restricted endpoints.
- Consider an external identity provider and Authorization Code with PKCE for production OAuth2 authentication. The password grant is not recommended for new OAuth2 systems.
```

**Learning by building.** This project is part of my journey to understand backend development, database management, authentication, and secure API development using Python and FastAPI.
