# Movies-API

## Overview
This project is a **Spring Boot** application that serves as an API for managing movies and reviews. The backend is connected to a **MongoDB** database, providing endpoints to:
- Retrieve all movies
- Get a movie by its ID
- Get a movie by its IMDb ID
- Post a review for a specific movie

## Features
- **Retrieve all movies:** Fetch details about all movies stored in the database.
- **Search by ID or IMDb ID:** Look up specific movies by unique identifiers.
- **Add reviews:** Post user reviews for a particular movie.

## Technologies Used
- **Spring Boot**
- **MongoDB**
- **Java**
- **Maven** (build tool)
- **RESTful API**

## Prerequisites
- **Java 17 or later**
- **Maven**
- **MongoDB** running locally or accessible via a connection string

---

### Configuration
In the `application.properties` file, configure the following:

```properties
spring.application.name=movies
spring.data.mongodb.database=movie-api-db
spring.data.mongodb.uri=mongodb+srv://vladutalexandru12:hNjjTLJ7m08QM91J@cluster0.er8wm.mongodb.net
```

---

## Endpoints

### **Get All Movies**
- **Endpoint:** `GET /movies`
- **Description:** Retrieves all movies from the database.
- **Response:**
  ```json
  [
    {
      "id": "12345",
      "title": "Movie Title",
      "releaseDate": "2023-01-01",
      "imdbId": "tt1234567",
      "reviews": []
    }
  ]
  ```

### **Get Movie by ID**
- **Endpoint:** `GET /movies/{id}`
- **Description:** Retrieves details of a specific movie by its ID.
- **Response:**
  ```json
  {
    "id": "12345",
    "title": "Movie Title",
    "releaseDate": "2023-01-01",
    "imdbId": "tt1234567",
    "reviews": []
  }
  ```

### **Get Movie by IMDb ID**
- **Endpoint:** `GET /movies/imdb/{imdbId}`
- **Description:** Retrieves a movie's details by its IMDb ID.
- **Response:**
  ```json
  {
    "id": "12345",
    "title": "Movie Title",
    "releaseDate": "2023-01-01",
    "imdbId": "tt1234567",
    "reviews": []
  }
  ```

### **Post Review**
- **Endpoint:** `POST /movies/{id}/reviews`
- **Description:** Adds a review to a specific movie.
- **Request Body:**
  ```json
  {
    "reviewer": "John Doe",
    "rating": 4.5,
    "comment": "Amazing movie!"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Review added successfully"
  }
  ```

---

## Running the Project
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/movies-api.git
   ```
2. Navigate to the project directory:
   ```bash
   cd movies-api
   ```
3. Build the project:
   ```bash
   mvn clean install
   ```
4. Run the application:
   ```bash
   mvn spring-boot:run
   ```
5. Access the API at `http://localhost:8080`.

---

## Database Schema
### Movies Collection
```json
{
  "_id": "ObjectId",
  "title": "String",
  "releaseDate": "String",
  "imdbId": "String",
  "reviews": [
    {
      "reviewer": "String",
      "rating": "Number",
      "comment": "String"
    }
  ]
}
```

---

## Testing the API
Use tools like **Postman**, **cURL**, or **Swagger** (if available) to test the endpoints.

---
