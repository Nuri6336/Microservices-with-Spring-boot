# Microservices-with-Spring-boot

Microservices with Spring Boot — learning project demonstrating microservice patterns using Spring Boot, Gradle and relational databases.

## Project Overview

This repository contains a set of Spring Boot microservices (Gradle-based) intended for learning and experimentation. The code demonstrates typical microservice concerns: service separation, inter-service communication, persistence with SQL, configuration and testing.

## Key Features

- Multiple Spring Boot services (independent modules)
- Gradle build and wrapper for reproducible builds
- Relational database usage (SQL) per service
- Unit and integration tests using Spring Test support
- Typical microservice patterns: REST APIs, DTOs, repositories, service layer

## Technology Stack

- Java (JDK 17+ recommended)
- Spring Boot (Spring Web, Spring Data JPA, Spring Boot Test)
- Gradle (with `gradlew` wrapper)
- SQL databases (H2 for tests / local, replaceable with PostgreSQL/MySQL)
- Optional: Docker / Docker Compose for multi-service orchestration

## Repository Structure (example)

- `service-a/` — a Spring Boot microservice (REST API, persistence)
- `service-b/` — another microservice
- `common/` — shared utilities / DTOs (optional)
- `build.gradle` / `settings.gradle` — Gradle multi-module configuration
- `README.md` — this file

Adjust the above to match actual module names in the repository.

## Getting Started (Windows)

1. Install JDK 17+ and Git.
2. From repository root, build the project:

- Using Gradle wrapper on PowerShell/Cmd:
    - `.\gradlew.bat clean build`
    - or `.\gradlew.bat test` to run tests

3. Run a service (example):

- From a service folder:
    - `cd service-a`
    - `.\gradlew.bat bootRun`

4. Access endpoints on `http://localhost:{port}` (each service configures its own port in `application.yml` / `application.properties`).

## Database

- Development: recommend H2 or an embedded DB for quick testing.
- Production: configure `spring.datasource.*` for PostgreSQL/MySQL and set appropriate JDBC URL, username and password via environment variables.
- Migration: add Flyway or Liquibase if schema management is needed.

## Configuration

- Per-service configuration is located in `src/main/resources/application.yml` or `application.properties`.
- Use profiles (e.g., `application-dev.yml`, `application-prod.yml`) and environment variables for secrets and per-environment settings.

## Testing

- Unit tests: run with `.\gradlew.bat test`
- Integration tests: annotate with `@SpringBootTest` and configure test containers or in-memory DB (H2) for reproducible runs.

## Common Commands

- Build all modules: `.\gradlew.bat clean build`
- Run a single service: `.\gradlew.bat :service-a:bootRun` (replace `service-a` with actual module)
- Run tests: `.\gradlew.bat test`
- Run an individual task: `.\gradlew.bat :module-name:taskName`

## Contributing

- Fork the repo, create a feature branch, make small focused commits and open a pull request.
- Include unit tests for new functionality.
- Keep services loosely coupled and well-documented.

## Notes

- Adapt module names, ports and DB configuration to match actual code in this repository.
- Consider adding Dockerfiles and a `docker-compose.yml` for local multi-service runs.

## License

Specify a license (e.g., MIT). Add `LICENSE` file to repository.
