# contact-us-api

Java Spring Boot REST API for contact form submissions with validation.

## Run locally

```sh
mvn spring-boot:run
```

The API listens on `http://localhost:8080`.

## Submit a contact message

Send a JSON request to `POST /api/contact`:

```sh
curl -i -X POST http://localhost:8080/api/contact \
	-H "Content-Type: application/json" \
	-d '{"name":"Ada Lovelace","email":"ada@example.com","message":"Hello!"}'
```

A valid request returns `202 Accepted` with `{"status":"accepted"}`. The `name`, `email`, and `message` fields are required; `email` must have a valid email format. Invalid requests return `400 Bad Request`.

## Run with Docker

```sh
docker build -t contact-us-api .
docker run --rm -p 8080:8080 contact-us-api
```

## Test

```sh
mvn test
```
