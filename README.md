# Lab 2: Books CRUD API Using Node.js, Express, and SQLite

## Student Details

- **Name:** A. Himaja
- **Registration Number:** 252U1R9008
- **Section:** CSE GAI-2A
- **Course:** Backend Development Fundamentals
- **Lab Number:** 02

## Live Deployment


## Objective

To develop a RESTful Books API using Node.js, Express.js, and SQLite to perform CRUD (Create, Read, Update, and Delete) operations on book records.

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

```text
lab-02/
├── screenshots/
│   ├── DELETE.png
│   ├── ERROR.png
│   ├── GET_ALL.png
│   ├── GETONE.png
│   ├── POST.png
│   └── PUT.png
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

2. Open the terminal in the `lab-02` directory.

3. Install the project dependencies:

   ```bash
   npm install
   ```

4. Start the development server:

   ```bash
   npm run dev
   ```

5. Send requests through Postman using the local server URL:

   ```text
   http://localhost:3000
   ```

   Use the appropriate HTTP methods and endpoints to test the Books CRUD API.

### Database Setup

The project uses SQLite to store book records.

- `books.db` is the SQLite database file.
- `books.sql` contains SQL statements related to the database.

The application connects to the database according to the implementation in `app.js`.

## API Endpoints

The following table describes the CRUD endpoints. Verify the exact paths and status codes against `app.js`.

| Method | Endpoint | Description | Expected Status |
|---|---|---|---|
| GET | `/books/` | Retrieves all books. | 200 OK |
| GET | `/books/:id/` | Retrieves a book using its ID. | 200 OK |
| POST | `/books/` | Adds a new book to the database. | 201 Created |
| PUT | `/books/:id/` | Updates an existing book. | 200 OK |
| DELETE | `/books/:id/` | Deletes a book using its ID. | 200 OK |

The application should also handle invalid requests and requests for books that do not exist, according to its implementation.

## Screenshots

The following screenshots demonstrate the API operations tested using Postman. Store them in the `screenshots/` directory.

### 1. GET All Books

Retrieves all book records from the database.

![GET all books](screenshots/GET_ALL.png)

### 2. GET a Single Book

Retrieves a specific book using its ID.

![GET one book](screenshots/GETONE.png)

### 3. POST a New Book

Adds a new book record to the database.

![POST book](screenshots/POST.png)

### 4. PUT an Existing Book

Updates the details of an existing book.

![PUT book](screenshots/PUT.png)

### 5. DELETE a Book

Deletes a book record from the database.

![DELETE book](screenshots/DELETE.png)

### 6. Error Handling

Demonstrates an error response for an invalid request or resource.

![API error response](screenshots/ERROR.png)

## CRUD Operations

- **Create:** Adds new book records using the POST method.
- **Read:** Retrieves all books or a specific book using GET.
- **Update:** Modifies existing book records using PUT.
- **Delete:** Removes book records using DELETE.

## HTTP Status Codes

- **200 OK:** The request was successful.
- **201 Created:** A new resource was created successfully.
- **400 Bad Request:** The request contains invalid input.
- **404 Not Found:** The requested resource or endpoint was not found.
- **500 Internal Server Error:** An unexpected server error occurred.

The actual status codes depend on the responses implemented in the application.

## Problems Faced and Solutions

Document any errors encountered while developing the application, connecting to the database, or testing the API, along with the solutions applied.

## Git and Repository Notes

- The project is maintained in the course GitHub repository.
- The `lab-02/` folder contains the files specific to Lab 2.
- The `.gitignore` file excludes `node_modules/` and `.env`.
- The `node_modules/` directory must not be committed.
- Screenshots are stored in the `screenshots/` directory.
- Changes are committed regularly with meaningful commit messages.
- The repository is public or shared with the faculty.

## Conclusion

The Books CRUD API was developed using Node.js, Express.js, and SQLite. It supports creating, retrieving, updating, and deleting book records. The API operations were tested using Postman.

