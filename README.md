# 📝 Small Note Manager

A simple yet powerful note management system built with **Spring Boot**. Designed as a learning project to master Spring Boot, this app allows users to create, manage, and view their notes securely, with admin capabilities to oversee all notes. My first Spring Boot adventure, and it was a wild ride! 😄

## ✨ Features
- **Authentication**:
  - Register: Create a new user account (`/auth/register`).
  - Login: Authenticate users with JWT tokens (`/auth/login`).
- **User Note Management**:
  - Create, update, and delete personal notes.
  - View all notes or specific note details (restricted to note owners).
- **Admin Dashboard**:
  - View all notes in the system (`/admin/notes/showall`).
- Secure RESTful APIs with Spring Security and JWT.
- Lightweight and beginner-friendly codebase.

## 🚀 Getting Started

### Prerequisites
- Java 17+ ☕
- Maven
- MySQL (for storing users and notes)
- IDE (e.g., IntelliJ IDEA, VS Code)

### Installation
1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/small-note-manager.git
