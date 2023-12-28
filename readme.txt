# ShareApp-UserService

## Table of Contents

1. [Overview](#overview)
2. [Features](#features)
3. [Prerequisites](#prerequisites)
4. [Getting Started](#getting-started)
5. [Project Structure](#project-structure)
6. [Usage](#usage)
7. [Testing](#testing)
8. [Contributing](#contributing)


## Overview

Your Project Name is a Node.js backend application designed for [mention briefly the main goal - authentication, user management, etc.]. It provides robust functionality for [mention key features].

## Features

1. **Authentication:**
   - Implements secure token-based authentication.
   - Supports Google OAuth2 authentication.

2. **Password Management:**
   - Change and reset passwords securely.

3. **User Management:**
   - User registration with validation.
   - Retrieve and update user information.

4. **Notification:**
   - Integration with a notification service for password reset.

## Prerequisites

Ensure you have the following installed:

- Node.js
- npm (Node Package Manager)
- [Other dependencies, tools, or services]

## Getting Started

Follow these steps to set up and run the project locally:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/ammar1616/ShareApp-userService.git
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Configure Environment Variables:**
   - Copy the `.env.example` file to `.env`.
   - Update the `.env` file with your configuration details.

4. **Run the Application:**
   ```bash
   npm start
   ```

## Project Structure

The project follows a modular structure:

- **controllers:** Handle business logic for different routes.
- **helpers:** Contains utility functions for location and notification.
- **middlewares:** Custom middleware functions, including error handling.
- **validations:** Data validation using Joi.
- **routes:** Define API routes for authentication and user management.
- **startup:** Initialization scripts for Firebase, Google OAuth, and route setup.


## Usage

To make use of the functionalities provided by **ShareApp-UserService**, follow the instructions below:

### 1. Authentication:

- **Login:**
  - Use the `/` endpoint with a POST request, providing valid credentials.
  - Example:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"email": "user@example.com", "password": "securepassword"}' http://localhost:5000/user-service/auth/
    ```

- **Token Verification:**
  - After logging in, you can verify the authenticity of your token by making a POST request to `/token`.
  - Example:
    ```bash
    curl -X POST -H "x-auth-token: [your_token_here]" http://localhost:5000/user-service/auth/token
    ```

- **Password Management:**
  - Change Password: Use the `/changePassword` endpoint with a POST request, providing the current and new passwords.
  - Reset Password: Use the `/resetPassword` endpoint with a POST request, providing the email address for password reset.

### 2. User Management:

- **Sign Up:**
  - Register a new user by making a POST request to the `/` endpoint with user details.
  - Example:
    ```bash
    curl -X POST -H "Content-Type: application/json" -d '{"name": "John Doe", "email": "john.doe@example.com", "password": "securepassword", "dob": "1990-01-01", "latitude": 51.340407, "longitude": 12.374052}' http://localhost:5000/user-service/user/
    ```

- **Get User Information:**
  - Retrieve user information by making a GET request to the `/` endpoint.
  - Example:
    ```bash
    curl -X GET -H "x-auth-token: [your_token_here]" http://localhost:5000/user-service/user/
    ```

- **Update User Information:**
  - Update user details by making a PATCH request to the `/` endpoint with the desired changes.
  - Example:
    ```bash
    curl -X PATCH -H "x-auth-token: [your_token_here]" -H "Content-Type: application/json" -d '{"name": "Updated Name", "dob": "1990-02-02"}' http://localhost:5000/user-service/user/
    ```


## Testing

To run tests, execute the following command:

```bash
npm test
```

The testing strategy includes unit tests for individual components, ensuring robustness and reliability.

## Contributing

We welcome contributions! Follow these guidelines to contribute to the project:

1. Fork the repository.
2. Create a new branch.
3. Make your changes and commit.
4. Submit a pull request.

Thanks for Your Interest