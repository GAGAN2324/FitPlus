# FitPlus (MicroFit)

A fitness tracking web application for managing workouts and monitoring personal fitness progress, built with a Spring Boot backend and a lightweight HTML/CSS/JS frontend.

## Features

- **User Authentication** — JWT-based login flow.
- **Workout Tracking** — log and view workouts tied to a user profile.
- **Dashboard** — view fitness stats and progress at a glance.

## Tech Stack

**Backend:** Java, Spring Boot, Spring Security, JWT, Spring Data JPA, MySQL
**Frontend:** HTML, CSS, vanilla JavaScript

## Project Structure

```
microfit/
├── src/main/java/com/microfit/microfit/
│   ├── controller/   # REST controllers (Auth, User, Workout)
│   ├── model/        # JPA entities
│   ├── dto/          # Request/response DTOs
│   ├── repository/   # Spring Data repositories
│   └── security/     # JWT + Spring Security config
└── MicroFrontend/    # Static HTML/CSS/JS frontend
```

## Getting Started

### Prerequisites
- Java 17+ and Maven
- MySQL running locally

### Configure the database
Update `src/main/resources/application.properties` with your local MySQL credentials:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/microfit
spring.datasource.username=root
spring.datasource.password=your_password
```

### Run the backend
```bash
mvn spring-boot:run
```
Runs on `http://localhost:8080`.

### Run the frontend
Open `MicroFrontend/login.html` via a local static server (e.g. IntelliJ's built-in web server, or `npx serve`).

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/auth/login` | Authenticate and receive a JWT |
| POST | `/api/auth/register` | Register a new user |
| GET/POST | `/api/users/**` | User CRUD operations |
| GET/POST | `/api/workouts/**` | Workout CRUD operations |

## Roadmap / Known Limitations

- Wire `/register` to actually persist users to the database
- Replace the hardcoded demo login check with real credential verification against the `User` table
- Add password hashing (BCrypt) before storing user passwords
