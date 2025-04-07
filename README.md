# Tasks Application

This is a Java-based application that implements a **Hexagonal Architecture** for managing tasks. It uses **Spring Boot** as the framework and **PostgreSQL** as the database.

## Features

- Create, retrieve, update, and delete tasks.
- Fetch additional task information from an external API.
- Implements Hexagonal Architecture principles for better modularity and testability.

## Technologies Used

- **Java 17**
- **Spring Boot 3.4.4**
- **PostgreSQL**
- **Maven**
- **Spring Data JPA**
- **RestTemplate** for external API calls

## Project Structure

The project follows the Hexagonal Architecture, dividing the code into the following layers:

1. **Domain**: Contains the core business logic and models.
2. **Application**: Implements use cases and services.
3. **Infrastructure**: Handles external integrations like database repositories, external APIs, and controllers.

### Key Directories

- `src/main/java/com/hexagonal/tasks/domain`: Core business logic and models.
- `src/main/java/com/hexagonal/tasks/application`: Use cases and services.
- `src/main/java/com/hexagonal/tasks/infrastructure`: Adapters, repositories, and controllers.
- `src/main/resources`: Configuration files like `application.properties`.

## How to Run

### Prerequisites

- Java 17 installed.
- PostgreSQL database running.
- Maven installed.

### Steps

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd tasks
   ```

2. Configure the database connection in 

application.properties

:
   ```properties
   spring.datasource.url=jdbc:postgresql://<host>:<port>/<database>
   spring.datasource.username=<username>
   spring.datasource.password=<password>
   ```

3. Build the project:
   ```bash
   ./mvnw clean install
   ```

4. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```

5. Access the API at 

http://localhost:8080/api/tasks

.

## API Endpoints

### Task Management

- **POST** 

tasks

: Create a new task.
- **GET** 

tasks

: Retrieve all tasks.
- **GET** `/api/tasks/{taskId}`: Retrieve a task by ID.
- **PUT** `/api/tasks/{taskId}`: Update a task by ID.
- **DELETE** `/api/tasks/{taskId}`: Delete a task by ID.

### Additional Task Info

- **GET** `/api/tasks/{taskId}/additionalInfo`: Fetch additional information about a task from an external API.

## External API Integration

The application integrates with the [JSONPlaceholder API](https://jsonplaceholder.typicode.com) to fetch additional task information.

## Testing

Run the tests using:
```bash
./mvnw test
```
