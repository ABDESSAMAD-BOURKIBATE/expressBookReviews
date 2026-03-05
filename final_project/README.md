# Express Book Reviews API

Welcome to the backend server implementation of the **Express Book Reviews API**.

This directory contains the entire source code and Node.js server setup required to run the project. The server handles all the requests and provides a seamless structure for users to view and review their favorite books.

### ✨ Features implementation check-list:
- [x] Node.js server setup with Express.js (`index.js`).
- [x] JSON Web Token (JWT) session-based authentication setup.
- [x] General Public API endpoints (`router/general.js`).
- [x] Authenticated Users API endpoints (`router/auth_users.js`).
- [x] Local Book Database (`router/booksdb.js`).
- [x] Search by ISBN, Author, and Title functionality implemented.
- [x] Add, Update, and Delete Review functionality configured.

---

### 📂 Directory Structure Overview

- **`index.js`**:
  The main entry point of the application. It initializes the Express server, sets up middleware including session-based authentication (`express-session`), and handles routing for the app.

- **`router/`**:
  This folder contains all the route modularization logic.
  - **`general.js`**: Contains public routes for fetching the list of books, getting book details by ISBN/Author/Title, viewing reviews, and registering new users.
  - **`auth_users.js`**: Contains authenticated routes exclusively for registered and logged-in users. It manages login via JWT and allows adding, modifying, or deleting book reviews.
  - **`booksdb.js`**: An in-memory local database (JSON format) containing details of various books to simulate database operations.

- **`test_general.js` & `test_auth.js`**:
  These testing scripts utilize the `Axios` library to perform HTTP requests (using Promises & Async/Await) to our Express API to verify data fetching operations.

---

### 📥 Usage Guide

1. Make sure you are in the `/final_project` directory.
2. Ensure you have installed all packages including `axios`, `express`, `jsonwebtoken`, and `express-session` by running `npm install`.
3. Start the application:
   ```bash
   npm start
   ```
4. On a separate terminal, to execute the automated tests:
   ```bash
   node test_general.js
   node test_auth.js
   ```

### 🔐 Environment & Security
- This project utilizes Session Authentication to keep registered users logged in securely.
- Only users bearing a valid token derived upon login can access the modification/deletion routes for book reviews.