# URL Shortener

This project is a simple URL Shortener service built with Go, using the Fiber framework, Redis for storage, and Docker for containerization.

## Project Structure

- **api/**: Contains the main application code.
  - **database/**: Manages the database connection.
  - **helpers/**: Utility functions to support the application.
  - **routes/**: Defines the application handlers for routes.
  - **Dockerfile**: Docker configuration for the API service.
  - **main.go**: Entry point for the API service.
- **db/**: Contains the Redis setup and its Docker configuration.
- **data/**: Directory for any persistent data storage.
- **compose.yaml**: Docker Compose configuration file to orchestrate the services.

## Features

- Shorten a URL by sending a POST request to `/api/v1`.
- Retrieve the original URL by sending a GET request to `/:url`.

## Setup and Usage

### Prerequisites

- Docker and Docker Compose installed on your machine.

### Running the Application

1. **Clone the repository**:
   ```bash
   git clone https://github.com/AramLab/url-shortener.git
   cd url-shortener
   ```
2. **Start the application using Docker Compose:**
    ```bash
    docker compose up --build
    ```
3. **API Endpoints:**
- POST `/api/v1`: Shorten a URL by passing it in the request body as JSON.
- GET `/:url`: Retrieve the original URL using the shortened path.

## Example Requests
- **Shorten a URL:**
```bash
curl -X POST http://localhost:3000/api/v1 -H "Content-Type: application/json" -d '{"url": "https://example.com"}'
```

- **Resolve a shortened URL:**
```bash
curl http://localhost:3000/<shortened_url>
```

## Built With:
- **Go:** The programming language used.
- **Fiber:** An Express-inspired web framework in Go.
- **Redis:** Used for storing the URL mappings.
- **Docker:** Containerization of the application.

