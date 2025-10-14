# 📚 LibroNova – Library Management System (JavaFX + JDBC)

**LibroNova** is a complete desktop application built with **Java SE 17+**, **JavaFX**, and **MySQL**.  
It provides a professional solution for library administration, including catalog management, user control, member (socio) registration, loan transactions, data persistence, CSV exports, and logging.  

This project was developed as part of a **Java SE performance assessment**, demonstrating advanced use of **OOP**, **layered architecture**, **JDBC transactions**, and **exception handling** in a real-world scenario.

---

## 🚀 Key Features

### 📖 Book Management
- CRUD operations for books: create, update, delete, and list.  
- ISBN uniqueness validation.  
- Stock and available copies update automatically (when books are loaned or returned).  
- Filter by **author** or **category**.  
- Export full catalog to CSV (`libros_export.csv`).  

---

### 👥 User & Authentication Module
- Role-based access control (**ADMIN / ASSISTANT**).  
- **Decorator pattern** adds default properties (role, active state, creation date).  
- Simulated HTTP logs for every CRUD operation.  
- Authentication with visual feedback and session control.  

---

### 🧾 Member (Socio) Management
- Register, edit, and remove members.  
- Validate duplicates by ID.  
- Export member list to CSV (`socios_export.csv`).  

---

### 🔁 Loan & Return Management
- Register new loans with **transaction control**.  
- Validate book stock and member activity before loan approval.  
- Automatic stock update on both loan and return.  
- Fine (penalty) calculation for overdue returns.  
- Export all loans or only overdue ones (`prestamos.csv` / `prestamos_vencidos.csv`).  

---

### ⚙️ Configuration & Files

- `config.properties` file defines:
  ```properties
  db.url=jdbc:mysql://localhost:3306/libronova
  db.user=root
  db.password=****
  diasPrestamo=7
  multaPorDia=1500

-- app.log records user actions and errors.

-- CSV export utilities for catalog, members, and loans.

### 🧩 Architecture & Design

-- Layered architecture:

-- controller → service → dao → model


Uses JavaFX for the interface instead of JOptionPane.

Exception-driven business validations.

Reusable utilities for DB connections, CSV handling, and logging.

### 🧪 Testing (JUnit 5)

-- Unit tests for business logic:
-- Fine calculation.
-- Stock and ISBN validation.

### Executed with Maven:

-- mvn test

### 🏗️ Project Structure
### src/main/java/com/libronova/
│
├── controller/        → JavaFX controllers (UI logic)
├── dao/               → Interfaces for database operations
├── dao/impl/          → JDBC implementations of DAOs
├── decorator/          → Decorator for user defaults
├── exception/          → Custom business and validation exceptions
├── model/              → POJO entities (Book, User, Member, Loan)
├── service/            → Business logic and transaction control
├── util/               → DB, CSV, Logging helpers
├── validation/         → Business rule validators
└── MainApp.java        → Application entry point

### 🧰 Technologies Used
Category - Technology
Language - Java SE 17+
Framework - JavaFX 21
Database - MySQL 8+
ORM / Persistence -	JDBC with transactions
Build Tool -	Apache Maven 3.9+
Testing -	JUnit 5
Logging -	java.util.logging
File Handling -	CSV & .properties
Architecture -	MVC / Layered Design

### ⚡ Setup Instructions

### 1️⃣ Database Configuration

-- Run the schema.sql script in MySQL Workbench or any client:

CREATE DATABASE libronova CHARACTER SET utf8mb4;
USE libronova;

-- Tables: usuarios, socios, libros, prestamos
-- Default admin user:
-- INSERT INTO usuarios (username, password, rol, activo)
-- VALUES ('admin', 'admin123', 'ADMIN', TRUE);

### 2️⃣ Configure config.properties

Located in:

### src/main/resources/config/config.properties

-- db.url=jdbc:mysql://localhost:3306/libronova
-- db.user=root
-- db.password=your_password
-- diasPrestamo=7
-- multaPorDia=1500

### 3️⃣ Build & Run

-- mvn clean install
-- mvn javafx:run

### 4️⃣ Login Credentials

-- Username: admin
-- Password: admin123
-- Role: ADMIN

💻 Interface Overview
Module - Description
Login -	Simple authentication with roles
Main Menu	- Navigation to Books, Users, Members, and Loans
Books	- CRUD, filtering, export
Members -	CRUD, export
Users -	CRUD with decorator and logging
Loans -	Register, return, calculate fines, export

All views are built with JavaFX FXML, styled with a consistent modern design and emoji-based feedback.

### 📂 CSV & Log Outputs

File - Purpose
libros_export.csv -	Full book catalog
socios_export.csv -	Member registry
prestamos.csv -	All loan records
prestamos_vencidos.csv - Overdue loans
app.log -	Application activity and error log

### 🧠 Business Rules Implemented

- ISBN must be unique.
- Available copies cannot exceed total stock.
- Members must be active to borrow books.
- Loans must respect configured due dates.
- Fines = (days late × multaPorDia).
- Database integrity guaranteed by transactions and rollback on failure.

### 🧑‍💻 Developer Notes

### Built and tested with:

- JDK 21
- JavaFX 21.0.3
- MySQL 8.0
- Maven 3.9.6


### ✅ Compatible with Windows, macOS, and Linux.

### 🏁 License

This project is released under the MIT License.
You’re free to use, modify, and distribute with proper attribution.

### 👨‍💻 Author

## Developed by:

-- Jonathan Andres Lopez Contreras
-- 1065854138
-- Cienaga
-- jonathandres0309@gmail.com

### 💼 Java Software Developer — OOP | JDBC | JavaFX | MySQL
