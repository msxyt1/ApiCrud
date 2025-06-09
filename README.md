# Java CRUD API

This project is a Spring Boot application that provides a RESTful API for performing CRUD (Create, Read, Update, Delete) operations on items. The API is documented using Swagger and can be run in a Docker container.

## Project Structure

```
java-crud-api
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── example
│   │   │           └── crudapi
│   │   │               ├── CrudApiApplication.java
│   │   │               ├── controller
│   │   │               │   └── ItemController.java
│   │   │               ├── model
│   │   │               │   └── Item.java
│   │   │               ├── repository
│   │   │               │   └── ItemRepository.java
│   │   │               └── service
│   │   │                   └── ItemService.java
│   │   └── resources
│   │       └── application.properties
│   └── test
│       └── java
│           └── com
│               └── example
│                   └── crudapi
│                       └── CrudApiApplicationTests.java
├── Dockerfile
├── docker-compose.yml
├── pom.xml
└── README.md
```

## Setup Instructions

1. **Clone the repository:**

mvn clean package

2. **Build the project:**
   ```
   docker build -t apicrud
   ```

3. **Run the application using Docker:**
   ```
docker run -p 8080:8080 apicrud
   ```

4. **Access the API:**
   The API will be available at `http://localhost:8080/api/items`.

5. **API Documentation:**
   Swagger UI can be accessed at `http://localhost:8080/swagger-ui.html`.

## API Endpoints

- **Create Item**
  - **POST** `/api/items`
  - Request Body: JSON representation of the item.

- **Get Item**
  - **GET** `/api/items/{id}`
  - Response: JSON representation of the item.

- **Update Item**
  - **PUT** `/api/items/{id}`
  - Request Body: JSON representation of the updated item.

- **Delete Item**
  - **DELETE** `/api/items/{id}`

## Dependencies

- Spring Boot
- Spring Data JPA
- Swagger for API documentation
- H2 Database (for development)

## Running Tests

To run the tests, use the following command:
```
mvn test
```

## License

This project is licensed under the MIT License.
