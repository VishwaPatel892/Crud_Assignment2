

# Notes Management API - Assignment 02

---

## 📮 Postman Documentation

👉 https://documenter.getpostman.com/view/50839289/2sBXwpPX2X


---

## 💻 GitHub Repository

👉 https://github.com/VishwaPatel892/Crud_Assignment2

---

## 📌 Objective

This project is a **REST API built using Express.js** that manages notes using **MongoDB with Mongoose**.

The API supports:

* Complete CRUD operations
* Route Parameters
* Query Parameters
* Pagination
* Sorting
* Bulk insert and bulk delete
* RESTful API design
* MVC architecture

---

## 🚀 Features

### CRUD Operations

* Create single note
* Create multiple notes
* Get all notes
* Get note by ID
* Replace note (PUT)
* Partial update (PATCH)
* Delete single note
* Delete multiple notes

### Route Parameters

* Filter notes by category
* Filter notes by pin status
* Get note summary

### Query Parameters

* General filtering
* Filter pinned notes
* Filter by category
* Filter by date range

### Pagination

* Paginate all notes
* Paginate notes by category

### Sorting

* Sort notes by different fields
* Sort pinned notes

---

## 🛠️ Tech Stack

* Node.js
* Express.js
* MongoDB
* Mongoose
* Postman

---

## 📂 Project Structure

```text
notes-app/
│
├── src/
│   ├── config/
│   │   └── db.js
│   │
│   ├── models/
│   │   └── note.model.js
│   │
│   ├── controllers/
│   │   └── note.controller.js
│   │
│   ├── routes/
│   │   └── note.routes.js
│   │
│   ├── middlewares/
│   │
│   ├── app.js
│   └── index.js
│
├── .env
├── .env.example
└── package.json
```

---

# API Endpoints

Base URL:

```text
/api/notes
```

---

## CRUD Endpoints

| Method | Endpoint          | Description             |
| ------ | ----------------- | ----------------------- |
| POST   | `/api/notes`      | Create a single note    |
| POST   | `/api/notes/bulk` | Create multiple notes   |
| GET    | `/api/notes`      | Get all notes           |
| GET    | `/api/notes/:id`  | Get note by ID          |
| PUT    | `/api/notes/:id`  | Replace note completely |
| PATCH  | `/api/notes/:id`  | Update note partially   |
| DELETE | `/api/notes/:id`  | Delete single note      |
| DELETE | `/api/notes/bulk` | Delete multiple notes   |

---

## Route Parameter Endpoints

| Method | Endpoint                        | Description                |
| ------ | ------------------------------- | -------------------------- |
| GET    | `/api/notes/category/:category` | Get notes by category      |
| GET    | `/api/notes/status/:isPinned`   | Get notes by pinned status |
| GET    | `/api/notes/:id/summary`        | Get note summary           |

---

## Query Parameter Endpoints

| Method | Endpoint                                                     | Description          |
| ------ | ------------------------------------------------------------ | -------------------- |
| GET    | `/api/notes/filter`                                          | General filtering    |
| GET    | `/api/notes/filter/pinned`                                   | Get pinned notes     |
| GET    | `/api/notes/filter/category?name=work`                       | Filter by category   |
| GET    | `/api/notes/filter/date-range?from=2024-01-01&to=2024-12-31` | Filter by date range |

---

## Pagination Endpoints

| Method | Endpoint                                 | Description             |
| ------ | ---------------------------------------- | ----------------------- |
| GET    | `/api/notes/paginate`                    | Paginate all notes      |
| GET    | `/api/notes/paginate/category/:category` | Paginate category notes |

---

## Sorting Endpoints

| Method | Endpoint                 | Description       |
| ------ | ------------------------ | ----------------- |
| GET    | `/api/notes/sort`        | Sort notes        |
| GET    | `/api/notes/sort/pinned` | Sort pinned notes |

---

# Query Parameters

## General Filter

```http
GET /api/notes/filter?category=work
```

```http
GET /api/notes/filter?isPinned=true
```

```http
GET /api/notes/filter?category=study&isPinned=false
```

---

## Date Range Filter

```http
GET /api/notes/filter/date-range?from=2024-01-01&to=2024-12-31
```

---

## Pagination

```http
GET /api/notes/paginate?page=1&limit=5
```

```http
GET /api/notes/paginate?page=2&limit=5
```

---

## Sorting

```http
GET /api/notes/sort?sortBy=title&order=asc
```

```http
GET /api/notes/sort?sortBy=createdAt&order=desc
```

```http
GET /api/notes/sort?sortBy=category&order=asc
```

---

# Response Format

Every endpoint follows the same structure:

```json
{
  "success": true,
  "message": "Operation successful",
  "data": []
}
```

---

## List Response

```json
{
  "success": true,
  "message": "Notes fetched successfully",
  "count": 10,
  "data": []
}
```

---

## Pagination Response

```json
{
  "success": true,
  "message": "Notes fetched successfully",
  "data": [],
  "pagination": {
    "total": 21,
    "page": 2,
    "limit": 5,
    "totalPages": 5,
    "hasNextPage": true,
    "hasPrevPage": true
  }
}
```

---

# Validation Rules

### Create Note

* Title is required
* Content is required

### Bulk Create

* `notes` array must exist
* `notes` array cannot be empty

### ID Routes

* Validate ObjectId first
* Return `400` if invalid
* Return `404` if note not found

### PATCH

* Request body cannot be empty

### Bulk Delete

* `ids` array must exist
* `ids` array cannot be empty

### Category Validation

Allowed values:

```text
work
personal
study
```

### Status Validation

Allowed values:

```text
true
false
```

---

# HTTP Status Codes

| Code | Description                          |
| ---- | ------------------------------------ |
| 200  | Successful GET, PUT, PATCH, DELETE   |
| 201  | Successful POST                      |
| 400  | Validation error / Invalid parameter |
| 404  | Resource not found                   |
| 500  | Internal server error                |

---

# Environment Variables

### .env

```env
MONGO_URI=your_mongodb_connection_string
PORT=5000
```

### .env.example

```env
MONGO_URI=your_mongodb_connection_string_here
PORT=5000
```

---

# Installation

### Clone Repository

```bash
git clone https://github.com/your-username/assignment-02-notes-api.git
```

### Move into Project Directory

```bash
cd notes-app
```

### Install Dependencies

```bash
npm install
```

### Start Development Server

```bash
npm run dev
```

### Start Production Server

```bash
npm start
```

Server will run on:

```text
http://localhost:5000
```

---

# Required Packages

```bash
npm install express mongoose dotenv
npm install --save-dev nodemon
```

---

# Submission

### Submit the Following

1. GitHub Repository Link
2. Postman Documentation Link
3. Live Render Deployment Link

---

## Author

**Vishwa Patel**

Backend Development Assignment 02
Node.js • Express.js • MongoDB • Mongoose
