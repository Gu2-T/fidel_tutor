# Laravel JWT Authentication System

## Overview
This is a **JWT-based authentication system** built with Laravel.  
It allows users to **register, login, logout, refresh tokens, and get their profile** securely via API endpoints.

This project is the backend foundation for the **LMS Tutor Registration System**, where secure user authentication is required.

---

## Features
- **User Registration**
  - Register new users with name, email, and password
  - Passwords are hashed securely
- **User Login**
  - Login using email and password
  - Returns a **JWT token** for authenticated requests
- **User Logout**
  - Invalidate JWT tokens
- **Token Refresh**
  - Refresh expired tokens to continue sessions
- **Get Authenticated User**
  - `/auth/me` endpoint returns the currently logged-in user
- **Validation**
  - Ensures proper email format and unique email on registration
  - Password confirmation and minimum length checks

---

## Tech Stack
- **Backend:** Laravel 11
- **Authentication:** JWT Auth (`php-open-source-saver/jwt-auth`)
- **Database:** MySQL / SQLite / PostgreSQL (configured in `.env`)
- **Version Control:** Git + GitHub

---


API Endpoints
| Endpoint         | Method | Description                    |
| ---------------- | ------ | ------------------------------ |
| `/auth/register` | POST   | Register a new user            |
| `/auth/login`    | POST   | Login and receive JWT token    |
| `/auth/logout`   | POST   | Logout user (invalidate token) |
| `/auth/refresh`  | POST   | Refresh JWT token              |
| `/auth/me`       | POST   | Get authenticated user info    |



Register
POST /auth/register
{
  "name": "John Doe",
  "email": "john@example.com",
  "password": "password123",
  "password_confirmation": "password123"
}



Login
POST /auth/login
{
  "email": "john@example.com",
  "password": "password123"
}


Response:

{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1...",
  "token_type": "bearer",
  "expires_in": 3600
}

