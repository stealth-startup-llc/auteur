# Universal Signup Login (USL)

This service provides a centralized authentication system for all users, both internal and external, ensuring secure access to our applications.

## Technologies Used

* **Leptos:** A full-stack Rust framework for building web applications.
* **Actix:** A powerful actor framework for Rust, used here for building the web server.
* **SurrealDB:** A versatile database offering flexibility and performance, used for storing user data.
* **bcrypt:** A library for password hashing, ensuring secure storage of sensitive information.

## Features

* Secure user registration and login with password hashing.
* SurrealDB integration for efficient user data management.
* Basic CRUD operations for user management.
* Foundation for future enhancements like social logins and advanced security features.

## Getting Started

### Prerequisites

* **Rust:** Install Rust using rustup: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`
* **SurrealDB:**  Install SurrealDB  and start the server: `surreal start --user admin --pass password`
  * Install https://surrealdb.com/docs/surrealdb/installation/macos

### Installation

1. Clone the repository: `git clone <repository_url>`
2. Navigate to the project directory: `cd universal-login-service`
3. Build and run the application: `cargo run`

### Usage

1. Access the application in your web browser: `http://127.0.0.1:8080`
2. Use the provided forms to register or log in.

## Database Schema

The SurrealDB schema for the user table is defined in `surrealdb/user_schema.surql`.  It uses `SCHEMAFULL` to ensure data integrity.

```surql
DEFINE TABLE user SCHEMAFULL;
```

## API Endpoints

* **POST /api/users:** Create a new user.
* **POST /api/login:** Log in an existing user.

## Security Considerations

* Passwords are hashed using bcrypt.
* Input validation is implemented to prevent malicious data.
* Future enhancements will include social login integration and other security measures.

## Future Enhancements

* Implement social logins using libraries like `openidconnect-rs` or `oauth2-rs`.
* Add more robust input validation and error handling.
* Implement features like password reset and two-factor authentication.
* Integrate with other services in the monorepo.

