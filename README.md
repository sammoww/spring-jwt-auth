# Spring JWT Authentication System

A complete implementation of JSON Web Token (JWT)-based authentication and authorization using **Spring Boot** and **Spring Security**. This project demonstrates how to secure RESTful APIs using JWT in a stateless manner.

---

## Features

- **User Registration and Login:**
  - Secure endpoints for user signup and login.
- **JWT Token Management:**
  - Token generation, validation, and expiration.
  - Integration with Spring Security to protect API endpoints.
- **Stateless Authentication:**
  - Implements stateless session management using JWT.
- **Role-Based Access Control (Optional):**
  - Easily extendable to include role-based access control.
- **Error Handling:**
  - Clear error messages for authentication and authorization issues.

---

## Getting Started

### Prerequisites

- Java 17 or higher
- Maven
- PostgreSQL (or any database of your choice)

### Running the Project

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/spring-jwt-auth.git
   cd spring-jwt-auth
   ```

2. **Configure the Application Properties:**
   Update the `src/main/resources/application.properties` file with your database and secret key configurations.
   ```properties
   spring.datasource.url=jdbc:postgresql://localhost:5432/your_db
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   jwt.secret=your_secret_key
   ```

3. **Build and Run the Application:**
   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

4. **Access the Endpoints:**
   - Base URL: `http://localhost:8081`
   - Swagger (Optional): `http://localhost:8081/swagger-ui.html`

---

## API Endpoints

### Authentication APIs

| Method | Endpoint                | Description                  |
|--------|-------------------------|------------------------------|
| POST   | `/api/v1/auth/register` | Register a new user          |
| POST   | `/api/v1/auth/login`    | Authenticate and get a token |

### Protected APIs

| Method | Endpoint                     | Description           |
|--------|------------------------------|-----------------------|
| GET    | `/api/v1/demo-controller/hello` | Sample protected endpoint |

Add the `Authorization` header with `Bearer <JWT_TOKEN>` to access protected endpoints.

---

## Project Structure

```
├── src/main/java/com/example/jwt
│   ├── auth
│   │   ├── AuthenticationController.java
│   │   ├── AuthenticationService.java
│   │   └── models (User, Role, etc.)
│   ├── config
│   │   ├── JwtAuthenticationFilter.java
│   │   ├── JwtService.java
│   │   ├── SecurityConfiguration.java
│   ├── demo
│   │   └── DemoController.java
├── src/main/resources
│   ├── application.properties
```

---

## Built With

- **Spring Boot** - Backend framework
- **Spring Security** - Security framework
- **PostgreSQL** - Database
- **JWT** - Token-based authentication
- **Maven** - Dependency management

---

## Future Improvements

- Add Swagger for API documentation.
- Extend role-based access control.
- Include refresh token implementation.


