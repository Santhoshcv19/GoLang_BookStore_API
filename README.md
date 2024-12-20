# GoLang BookStore API

## Overview
The **GoLang BookStore API** is a simple RESTful API built with the Gin web framework. It manages a collection of books and allows users to perform various operations, such as listing available books, adding a new book, checking out a book, and returning a book.

## Features
- Retrieve all books in the bookstore.
- Get details of a specific book by its ID.
- Add a new book to the collection.
- Check out a book (decrease its quantity).
- Return a book (increase its quantity).

## Technologies Used
- Programming Language: Go (Golang)
- Framework: [Gin Web Framework](https://github.com/gin-gonic/gin)

## Installation
1. Install [Go](https://golang.org/dl/).
2. Clone this repository:
   ```bash
   git clone <repository-url>
   ```
3. Navigate to the project directory:
   ```bash
   cd GoLang_BookStore_API
   ```
4. Install dependencies:
   ```bash
   go mod init bookstore-api
   go get -u github.com/gin-gonic/gin
   ```

## Usage
1. Run the API:
   ```bash
   go run main.go
   ```
2. The server will start at `http://localhost:8000`.

## Endpoints

### 1. **Get All Books**
- **URL:** `/books`
- **Method:** GET
- **Response:** JSON array of all books.

#### Example Response:
```json
[
  {
    "id": "1",
    "title": "In Search of Lost Time",
    "author": "Marcel Proust",
    "quantity": 2
  },
  {
    "id": "2",
    "title": "The Great Gatsby",
    "author": "F. Scott Fitzgerald",
    "quantity": 5
  }
]
```

### 2. **Get Book by ID**
- **URL:** `/books/:id`
- **Method:** GET
- **Parameters:**
  - `id` (path parameter): ID of the book.
- **Response:** JSON object of the requested book or error message.

#### Example Response:
```json
{
  "id": "1",
  "title": "In Search of Lost Time",
  "author": "Marcel Proust",
  "quantity": 2
}
```

### 3. **Add a New Book**
- **URL:** `/books`
- **Method:** POST
- **Request Body:** JSON object containing book details.

#### Example Request:
```json
{
  "id": "4",
  "title": "1984",
  "author": "George Orwell",
  "quantity": 10
}
```

#### Example Response:
```json
{
  "id": "4",
  "title": "1984",
  "author": "George Orwell",
  "quantity": 10
}
```

### 4. **Check Out a Book**
- **URL:** `/checkout`
- **Method:** PATCH
- **Query Parameters:**
  - `id`: ID of the book to check out.
- **Response:** JSON object of the updated book or error message.

#### Example Response:
```json
{
  "id": "1",
  "title": "In Search of Lost Time",
  "author": "Marcel Proust",
  "quantity": 1
}
```

### 5. **Return a Book**
- **URL:** `/return`
- **Method:** PATCH
- **Query Parameters:**
  - `id`: ID of the book to return.
- **Response:** JSON object of the updated book or error message.

#### Example Response:
```json
{
  "id": "1",
  "title": "In Search of Lost Time",
  "author": "Marcel Proust",
  "quantity": 3
}
```

## Error Responses
- **404 Not Found:**
  - Book not found.
  ```json
  {
    "message": "Book not found!"
  }
  ```
- **400 Bad Request:**
  - Missing or invalid query parameter.
  ```json
  {
    "message": "Missing id query parameter"
  }
  ```

## Future Improvements
- Add database integration for persistent storage.
- Implement user authentication and authorization.
- Add pagination and filtering for the `/books` endpoint.
- Include more detailed error handling.

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## Author
[C V Santhosh](https://github.com/Santhoshcv19)

