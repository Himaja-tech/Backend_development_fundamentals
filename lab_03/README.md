# Lab 3: Advanced Books CRUD API Using Node.js, Express, and SQLite

## Student Details
- **Name:** A. Himaja
- **Registration Number:** 252U1R9008
- **Section:** CSE GAI-2A
- **Course:** Backend Development Fundamentals
- **Lab Number:** 03

## Live Deployment
https://backend-development-fundamentals-3-wq00.onrender.com

## Objective
To develop an advanced RESTful Books API using Node.js, Express.js, and SQLite. The application supports CRUD (Create, Read, Update, and Delete) operations along with searching, sorting, filtering, pagination, input validation, and error handling.

## Technologies Used
- Node.js
- Express.js
- SQLite
- JavaScript
- npm
- Postman
- Visual Studio Code
- Git and GitHub

## Project Structure
lab_03/
├── screenshots/
│   ├── book-not-found.png
│   ├── delete.png
│   ├── filter-books-by-price.png
│   ├── get_all.png
│   ├── get_one.png
│   ├── invalid-book-id.png
│   ├── pagination-books.png
│   ├── post.png
│   ├── put.png
│   ├── search-books.png
│   └── sort-books.png
├── .gitignore
├── app.js
├── books.db
├── books.sql
├── package.json
├── package-lock.json
└── README.md
```

## Installation and Setup

### Prerequisites

- **Node.js:** Required to run the application.
- **npm:** Used to install and manage project dependencies. It is included with Node.js.
- **Visual Studio Code:** Recommended for editing and managing project files.
- **Postman:** Used to test API endpoints and verify responses.
- **Git:** Used to clone the repository and manage version control.

**Note:** The application uses SQLite through its Node.js dependencies. A separate SQLite installation may not be required.

### Steps to Run

1. Clone the course repository or download the project.

2. Open the terminal in the `lab_03` directory.

3. Install the project dependencies:

   ```bash
   npm install
   ```

4. Start the application:

   ```bash
   node app.js
   ```

5. The server runs at:

   ```text
   http://localhost:3000
   ```

6. Use Postman to send requests to the API endpoints.

## Database Setup

The project uses SQLite to store book records.

- `books.db` is the SQLite database file.
- `books.sql` contains SQL statements for creating and managing the book table.
- The `book` table stores book ID, title, author, price, and number of pages.
- The application automatically creates the table if it does not exist.
- Ten sample book records are inserted when the database is empty.

### Database Table Structure

| Column | Data Type | Description |
|---|---|---|
| id | INTEGER | Primary key with auto-increment |
| title | TEXT | Name of the book |
| author | TEXT | Book author |
| price | INTEGER | Price of the book |
| pages | INTEGER | Number of pages |

## API Endpoints

| Method | Endpoint | Description | Expected Status |
|---|---|---|---|
| GET | `/books` | Retrieves all books with additional features | 200 OK |
| GET | `/books/:bookId` | Retrieves a specific book using its ID | 200 OK |
| POST | `/books` | Adds a new book | 201 Created |
| PUT | `/books/:bookId` | Updates an existing book | 200 OK |
| DELETE | `/books/:bookId` | Deletes a book using its ID | 200 OK |

## Additional GET API Features

The GET `/books` endpoint supports the following query parameters.

### 1. Search Books

Searches for books based on their titles.

```text
GET /books?search_q=Silent
```

### 2. Sorting Books

Sorts book records using a selected column and sorting order.

GET /books?order_by=price&order=DESC
Supported sorting columns:
- id
- title
- author
- price
- pages

Sorting orders:
- ASC – Ascending order
- DESC – Descending order

### 3. Filtering Books by Price
Retrieves books within a specified price range.
GET /books?min_price=300&max_price=400
```

### 4. Pagination
Retrieves a limited number of records using limit and offset.
GET /books?limit=3&offset=0
- `limit` specifies the maximum number of records.
- `offset` specifies the number of records to skip.

### 5. Combining Query Parameters
Multiple features can be used together.
GET /books?search_q=The&min_price=200&max_price=400&order_by=price&order=ASC&limit=5&offset=0
```

## Screenshots

The following screenshots demonstrate the API operations tested using Postman. They are stored in the `screenshots/` directory.

### 1. GET All Books

Retrieves all book records from the database.

![GET all books](screenshots/get_all.png)

### 2. GET a Single Book

Retrieves a specific book using its ID.

![GET one book](screenshots/get_one.png)

### 3. POST a New Book

Adds a new book record to the database.

![POST book](screenshots/post.png)

### 4. PUT an Existing Book

Updates the details of an existing book.

![PUT book](screenshots/put.png)

### 5. DELETE a Book

Deletes an existing book record.

![DELETE book](screenshots/delete.png)

### 6. Search Books

Searches for books using the title query parameter.

![Search books](screenshots/search-books.png)

### 7. Sort Books

Displays books sorted by the selected column and order.

![Sort books](screenshots/sort-books.png)

### 8. Filter Books by Price

Retrieves books based on minimum and maximum price.

![Filter books](screenshots/filter-books-by-price.png)

### 9. Pagination

Retrieves a specified number of books using limit and offset.

![Pagination](screenshots/pagination-books.png)

### 10. Invalid Book ID

Demonstrates validation when an invalid book ID is provided.

![Invalid book ID](screenshots/invalid-book-id.png)

### 11. Book Not Found

Demonstrates the 404 response when a requested book does not exist.

![Book not found](screenshots/book-not-found.png)

## CRUD Operations

- **Create:** Adds new book records using the POST method.
- **Read:** Retrieves all books or a specific book using GET.
- **Update:** Modifies existing book records using PUT.
- **Delete:** Removes book records using DELETE.

## HTTP Status Codes

- **200 OK:** The request was successful.
- **201 Created:** A new book record was created successfully.
- **400 Bad Request:** The request contains invalid input.
- **404 Not Found:** The requested book does not exist.
- **500 Internal Server Error:** An unexpected server error occurred.

## Viva Questions (Be Ready to Answer)

### 1. What is the difference between Query Parameters and Path Parameters?

**Path Parameters:**
- Used to identify a specific resource.
- Example: `GET /books/5`
- Here, `5` represents the book ID.
- In Express.js, they are accessed using `request.params`.

**Query Parameters:**
- Used for searching, filtering, sorting, and pagination.
- Example: `GET /books?search_q=Silent&order=ASC`
- Here, `search_q` and `order` are query parameters.
- In Express.js, they are accessed using `request.query`.

### 2. What does Stateless mean?

Stateless means that the server does not depend on information from previous requests to process a new request. Each request must contain all the necessary information required for processing.

In REST APIs, every request is handled independently.

### 3. Which HTTP Status Codes are used for Bad Input and a Missing Record?

**400 Bad Request:**
- Returned when the client sends invalid input or incorrect parameters.
- Example: `GET /books/abc`
- Response: `Invalid book ID`

**404 Not Found:**
- Returned when the requested resource does not exist.
- Example: `GET /books/999`
- Response: `Book not found`

**Remember:**

- 200 – Successful request.
- 201 – Resource created successfully.
- 400 – Invalid request.
- 404 – Resource not found.
- 500 – Internal server error.

## Problems Faced and Solutions
- **Database Initialization:** Ensured that the book table is created automatically when the application starts.
- **Existing Database Records:** Used a record count check to insert sample books only when the database is empty.
- **Invalid User Inputs:** Added validation for book details, price, pages, sorting parameters, and pagination values.
- **SQL Query Construction:** Used parameterized queries for user-provided values to improve database security.
- **Search and Filtering:** Used SQL conditions to support title searching and price filtering.
- **Sorting and Pagination:** Implemented dynamic sorting with allowed column validation and limit-offset pagination.

## Git and Repository Notes
- The project is maintained in the course GitHub repository.
- The `lab_03/` folder contains the files specific to Lab 3.
- The `.gitignore` file excludes `node_modules/` and `.env`.
- The `node_modules/` directory must not be committed.
- API screenshots are stored in the `screenshots/` directory.
- Changes are committed regularly with meaningful commit messages.
- The repository is public or shared with the faculty.

## Conclusion
The Advanced Books CRUD API was successfully developed using Node.js, Express.js, and SQLite. The application supports creating, retrieving, updating, and deleting book records. Additional features such as searching, sorting, price filtering, and pagination were implemented. Input validation and error handling were also added to improve the reliability and security of the API. All major API functionalities were tested using Postman.