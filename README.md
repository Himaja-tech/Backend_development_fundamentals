
# Lab 1: Node.js and Express server

## Student Details
- Name: Himaja
- Registration Number: A.Himaja
- Section: CSE GAI-

## Live Link
Not deployed yet.

## Objective
To create a Node.js HTTP server and an Express server with multiple routes.

## Technologies Used
- Node.js
- Express.js
- JavaScript
- npm

## How to Run

1. Install Node.js.
2. Open the terminal in this folder.
3. Install dependencies:

   ```bash
   npm install
   ```

4. Start the Express server:

   ```bash
   node server.js
   ```

5. Open http://localhost:3000 in your browser.

## Endpoints

| Method | Path | Description | Status Code |
|---|---|---|---|
| GET | / | Welcome message | 200 |
| GET | /about | Displays name and section | 200 |
| GET | /time | Displays current date and time | 200 |
| GET | /anything | Handles unknown routes | 404 |

## Screenshots

### Home Route
![Home route](screenshots/home.png)

### Welcome Route
![Welcome route](screenshots/welcome.png)

### About Route
![About route](screenshots/about.png)

### Time Route
![Time route](screenshots/time.png)

### 404 Route
![404 route](screenshots/not-found.png)

## Problems Faced and Solutions
I learned how to create a Node.js server and an Express server,
define routes, and return the correct HTTP status codes.
