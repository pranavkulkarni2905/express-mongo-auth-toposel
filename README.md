# Express.js User Authentication API

This is a **Node.js + Express.js + MongoDB** backend API for user authentication. It allows users to **register**, **log in**, and **search users** using **JWT authentication**.

## Features
- User **Registration** with **secure password hashing**.
- User **Login** with JWT-based authentication.
- **Search Users** by username or email (protected route).
- **MongoDB** as the database.
- **JWT Token** for authentication.
- **Data validation** on the server-side.

---

## Tech Stack Used
- **Node.js** + **Express.js** (Backend)
- **MongoDB** (Database)
- **Mongoose** (ODM)
- **bcrypt.js** (Password Hashing)
- **jsonwebtoken (JWT)** (Authentication)
- **dotenv** (Environment Variables)
- **Postman** (API Testing)

---
## Screenshots
- Database MongoDB
  ![image](https://github.com/user-attachments/assets/71c58c1e-de13-45cc-9cb5-9484645a21e3)
- Postman API Testing

  ![image](https://github.com/user-attachments/assets/1917d401-25fe-4adc-88dc-51e5747695be)

  ![image](https://github.com/user-attachments/assets/7803a913-c2a1-42b0-8d05-a6a50cf50ea6)

  ![image](https://github.com/user-attachments/assets/dc13a59a-3619-43d8-9e51-7d2676da340d)





## Installation & Setup

### 1️⃣ Clone the Repository
```sh
git clone https://github.com/pranavkulkarni2905/express-mongo-auth-toposel.git
cd express-mongo-auth
```

### 2️⃣ Install Dependencies
```
npm install
```
### 3️⃣ Configure Environment Variables
Create a .env file in the project root:

```
PORT=5000
MONGO_URI=your_uri
JWT_SECRET=your_jwt_secret_key
```
### 4️⃣ Start the Server
For development (auto-restart using nodemon):
```
npm run dev
```
## API Endpoints
### 📌 1. Register User
Endpoint: POST /api/auth/register
- Request Body (JSON):

```
{
  "username": "john_doe",
  "email": "john@example.com",
  "password": "SecurePass123",
  "fullName": "John Doe",
  "gender": "Male",
  "dateOfBirth": "1995-06-15",
  "country": "USA"
}
```
- Response:

```
{
  "message": "User registered successfully"
}
```
### 📌 2. Login User
Endpoint: POST /api/auth/login
- Request Body (JSON):
```
{
  "email": "john@example.com",
  "password": "SecurePass123"
}
```
- Response:

```
{
  "token": "your_jwt_token_here",
  "user": {
    "_id": "65babc1234cde5678f901234",
    "username": "john_doe",
    "email": "john@example.com",
    "fullName": "John Doe",
    "gender": "Male",
    "dateOfBirth": "1995-06-15T00:00:00.000Z",
    "country": "USA",
    "createdAt": "2025-02-13T12:34:56.789Z",
    "updatedAt": "2025-02-13T12:34:56.789Z"
  }
}
```

### 📌 3. Search User (Protected Route)
Endpoint: GET /api/auth/search?query=username_or_email
- Headers:

```
Authorization: Bearer your_jwt_token_here
```
- Response Example:

```
{
  "_id": "65babc1234cde5678f901234",
  "username": "john_doe",
  "email": "john@example.com",
  "fullName": "John Doe",
  "gender": "Male",
  "dateOfBirth": "1995-06-15T00:00:00.000Z",
  "country": "USA",
  "createdAt": "2025-02-13T12:34:56.789Z",
  "updatedAt": "2025-02-13T12:34:56.789Z"
}
```
### 🛠 Testing with Postman
- Register a user → Send a POST request to /api/auth/register with the JSON body.
- Login → Send a POST request to /api/auth/login. Copy the JWT token from the response.
- Search User → Send a GET request to /api/auth/search?query=username_or_email with Authorization header (Bearer token).

## 🚀 Deployment 
To deploy this project:

- MongoDB Atlas for database hosting.
- Render for Express.js API hosting.

## 📌 Author
- Pranav kulkarni

- Email: pranavkulkarni1110@gmail.com
