📝 Small Note Manager
A simple and lightweight note management system built with Spring Boot. This project was my first dive into Spring Boot, created to learn its fundamentals while building a functional app for managing notes. It’s been a fun (and sometimes challenging!) journey! 😄
✨ Features

Authentication:
Register new users and log in securely with JWT tokens.


User Note Management:
Create, update, delete, and view personal notes.
View all notes or specific note details (restricted to note owners).


Admin Dashboard:
View all notes in the system (admin-only).


Secure RESTful APIs with Spring Security and JWT.
Lightweight and beginner-friendly codebase.

🚀 Getting Started
Prerequisites

Java 17+ ☕
Maven
MySQL (for storing users and notes)
IDE (e.g., IntelliJ IDEA, VS Code)

Installation

Clone the repository:git clone https://github.com/your-username/small-note-manager.git


Navigate to the project directory:cd small-note-manager


Configure the database:
Ensure MySQL is running locally.
Create a database named smallnote.
Update src/main/resources/application.properties with your database credentials:spring.datasource.url=jdbc:mysql://localhost:3306/smallnote
spring.datasource.username=your-username
spring.datasource.password=your-password
spring.jpa.hibernate.ddl-auto=update
jwt.secret=your-jwt-secret-key



Note: Replace your-jwt-secret-key with a secure key for JWT signing (e.g., a 32-character string).

Build and run the application:mvn spring-boot:run


Access the app:
Test APIs using Postman or curl (see endpoints below).
Admin endpoint: http://localhost:8080/admin/notes/showall (requires admin authentication).



🛠️ Tech Stack

Backend: Spring Boot, Spring Data JPA, Spring Security
Database: MySQL
Authentication: JSON Web Tokens (JWT)
Build Tool: Maven
Other: RESTful APIs, JSON responses

📚 API Endpoints
Below is the complete list of API endpoints for the Small Note Manager:
Authentication



Method
Endpoint
Description
Request Body
Response



POST
/auth/register
Register a new user
{ "name": "string", "account": "string", "password": "string" }
String (e.g., "Create Account Success.")


POST
/auth/login
Authenticate a user (returns JWT)
{ "account": "string", "password": "string" }
LoginResponse (message, token)


User Note Management



Method
Endpoint
Description
Request Body
Response



POST
/user/notes/create
Create a new note
{ "title": "string", "content": "string" }
String (e.g., "Note created.")


POST
/user/notes/update/{id}
Update an existing note
{ "title": "string", "content": "string" }
String (e.g., "Update Note Success.")


POST
/user/notes/delete/{id}
Delete a note
-
String (e.g., "Delete Note Success.")


GET
/user/notes/view
View all user’s notes
-
BaseResponse (message, list of NoteResponse)


GET
/user/notes/view/details/{id}
View a specific note (owner only)
-
BaseResponse (message, NoteResponse)


Admin



Method
Endpoint
Description
Request Body
Response



GET
/admin/notes/showall
View all notes in the system
-
List<NoteResponse>


Notes: 

Protected endpoints (/user/*, /admin/*) require a JWT token in the Authorization header: Bearer <token>.
Obtain the token via /auth/login.
Admin endpoints require appropriate roles/permissions (configured in your AdminServiceImpl).
All endpoints are accessible at http://localhost:8080 when running locally.

📸 Screenshots
(Coming soon! Add Postman screenshots or UI if available.)
🤝 Contributing
Contributions are welcome! 😊 To contribute:

Fork the repo.
Create a new branch (git checkout -b feature/your-feature).
Commit your changes (git commit -m 'Add cool feature').
Push to the branch (git push origin feature/your-feature).
Open a Pull Request.

📜 License
MIT License. See LICENSE for details.
🙌 Acknowledgments

Huge thanks to the Spring Boot and Spring Security communities for amazing docs and tutorials!
Built with 💖 as a learning project to conquer Spring Boot challenges.


Author: [Your Name] – your-email@example.comProject Link: [Link to your GitHub repo]
