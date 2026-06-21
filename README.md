# Student Web Service with JWT

A project developed for the **Web Programming 2** course, focused on user authentication with JWT, in-memory data storage, and protected routes using Express.js.

## About the Project

A REST API built with Node.js and Express. It allows users to register and log in with JWT. Once authenticated, users can access protected routes to manage student records.

All data (users and students) is stored in **in-memory arrays**. The student `id` is provided manually in the request body.

## Features

- **/register**: User registration with encrypted password (bcrypt).
- **/login**: Generates a JWT valid for 1 hour.
- **/alunos** (students):
  - `GET`: List all students (protected)
  - `POST`: Add a student (protected)
  - `PUT /alunos/:id`: Update a student (protected)
  - `DELETE /alunos/:id`: Remove a student (protected)
  - `GET /alunos/:id`: Retrieve a specific student (protected)
  - `GET /alunos/medias`: Return the name and grade average for all students (protected)
  - `GET /alunos/aprovados`: Return the name and approval status for all students (protected)

## Technologies

- **Node.js**
- **Express.js**
- **JWT**
- **BcryptJS**
- **dotenv**

## Project Structure

```
student-webservice/
├── .env
├── server.js
├── alunos.js
├── package.json
└── README.md
```

## Notes

- No database — data is stored in in-memory arrays only.
- The student `id` must be provided in the request body.
- The JWT token goes in the header: `Authorization: Bearer <token>`

## Examples

**User Registration (POST /register)**

```json
{
  "username": "admin",
  "password": "123456"
}
```

**Login (POST /login)**

```json
{
  "username": "admin",
  "password": "123456"
}
```

Response:
```json
{
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6..."
}
```

**Add Student (POST /alunos)**

Header:
```
Authorization: Bearer <token>
```

Body:
```json
{
  "id": 1,
  "nome": "Leo Freitas",
  "curso": "Software Engineering"
}
```

## Credits

Project developed for the **PRW2 (Web Programming 2)** course.
