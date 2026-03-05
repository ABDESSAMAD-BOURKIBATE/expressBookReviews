# IBM Full Stack Software Developer - Express Book Reviews 📚

![Node.js](https://img.shields.io/badge/Node.js-18.x-green?style=for-the-badge&logo=node.js)
![Express](https://img.shields.io/badge/Express-4.x-lightgrey?style=for-the-badge&logo=express)
![JWT](https://img.shields.io/badge/JWT-JSON%20Web%20Tokens-black?style=for-the-badge&logo=json-web-tokens)
![NPM](https://img.shields.io/badge/NPM-red?style=for-the-badge&logo=npm)

A complete RESTful API built with **Node.js** and **Express.js** for managing a book review system. This project is the final assignment for the Back-End Development module of the IBM Full Stack Software Developer Professional Certificate on Coursera.

## 📖 Project Overview

This API provides public endpoints to browse a library of books and authenticated endpoints for registered users to manage their book reviews. The server utilizes `express-session` and `jsonwebtoken (JWT)` to securely manage authentication and user sessions.

### Key Features
- **Public Users:**
  - View all books available in the shop.
  - Search for books by **ISBN**.
  - Search for books by **Author**.
  - Search for books by **Title**.
  - Read existing book reviews.
  - Register as a new user.

- **Authenticated Users:**
  - Secure Login with JSON Web Tokens (JWT).
  - Add a new review to a book.
  - Modify a completed review.
  - Delete their own review.
  - Multiple users can review the same book independently.

---

## 🛠️ Architecture and Endpoints

### 1. General Routes (Public)
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/` | Retrieve the entire list of books. |
| `GET` | `/isbn/:isbn` | Retrieve details of a specific book by its ISBN. |
| `GET` | `/author/:author` | Retrieve books written by a specific author. |
| `GET` | `/title/:title` | Retrieve books with a specific title. |
| `GET` | `/review/:isbn` | Retrieve all reviews for a specific book. |
| `POST` | `/register` | Register a new user in the system. |

### 2. Authenticated Routes (Private)
*Requires users to be logged in and possess a valid JWT session token.*

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `POST` | `/customer/login` | Login with username and password to get a token. |
| `PUT` | `/customer/auth/review/:isbn` | Add or update a review for a specific book. |
| `DELETE`| `/customer/auth/review/:isbn` | Delete the logged-in user's review for a book. |

---

## 🚀 Setup & Installation

### Prerequisites
Make sure you have [Node.js](https://nodejs.org/) installed on your machine.

### Installation Steps

1. **Clone the project / Navigate to directory:**
   ```bash
   cd final_project
   ```

2. **Install all dependencies:**
   ```bash
   npm install
   ```

3. **Install Axios (Required for Testing Scripts):**
   ```bash
   npm install axios
   ```

4. **Start the Express Server:**
   ```bash
   npm start
   ```
   *The server will start on `http://localhost:5000`*

---

## 🧪 Testing the API

As required by the IBM course rubric, data fetching is demonstrated using `Promises` and `async/await` with `Axios`. The project includes two testing scripts to verify all endpoints are working correctly.

### 1. Testing Public Endpoints
Run the `test_general.js` script to test fetching books, authors, and titles:
```bash
node test_general.js
```

### 2. Testing Authentication Endpoints
Run the `test_auth.js` script to test user registration and login:
```bash
node test_auth.js
```

### Manual Testing with Postman / cURL
You can also test the endpoints manually using Postman.
- **Example cURL to get all books:**
  ```bash
  curl -s http://localhost:5000/
  ```

---

## 💻 Tech Stack
- **Backend Framework:** Express.js
- **Runtime Environment:** Node.js
- **Authentication:** jsonwebtoken (JWT), express-session
- **HTTP Client (for testing):** Axios

## 📝 License
This project is licensed under the MIT License - see the LICENSE file for details.