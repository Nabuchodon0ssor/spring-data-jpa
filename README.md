# 🚀 Spring Boot REST API with Spring Data JPA (Employee Management)

🌐 RESTful CRUD application built with Spring Boot using Spring Data JPA for database access.

This project demonstrates how to simplify the persistence layer by replacing manual DAO implementation with Spring Data JPA repositories.

---

## 📌 Project Overview

This is a **Spring Boot REST application** that provides endpoints to manage employees.

- Backend-focused REST API
- JSON-based communication
- Built with Spring Boot and embedded server
- Designed following REST principles and layered architecture

The application follows a layered architecture:

Controller → Service → Repository → Entity

## ✨ Features

- ✅ Full CRUD operations (Create, Read, Update, Delete)
- 🌐 RESTful API design
- 📦 JSON data exchange
- 🗄 Database interaction using Spring Data JPA
- ⚡ Reduced boilerplate code (no DAO implementation)
- 🔍 Custom query methods (e.g. `findAllByName`)
- ⚙️ Spring Boot auto-configuration
- 🚀 Embedded Tomcat (no manual deployment)

## Screenshots

### Employee List
![Employee List](images/Screenshot.png)

## 🛠 Requirements

- ☕ Java 8 or higher
- 📦 Maven
- 🐬 MySQL 8.x
- 💡 IntelliJ IDEA (recommended)

## 🚀 How to Run

### 1️⃣ Clone the repository

Clone this repository to your local machine:
```bash
git clone https://github.com/YOUR_USERNAME/spring-data-jpa.git
```

Or download it as a ZIP archive and extract it.

### 2️⃣ Open the project in IntelliJ IDEA

- Open IntelliJ IDEA
- Select File → Open
- Choose the root project folder spring_course_rest
- IntelliJ will automatically detect two Maven modules
- Make sure all Maven dependencies are downloaded successfully

### 3️⃣ Install and configure MySQL

Make sure **MySQL is installed and running** on your computer.

- MySQL version: **8.x**
- Default port: **3306**

You can check MySQL installation by running:

```bash
mysql --version
```

Or by opening MySQL Workbench.

### 4️⃣ Create a local database

Open MySQL Workbench (or terminal) and run:

```sql
CREATE DATABASE my_db;
USE my_db;
```
Create table
```sql
CREATE TABLE employees (
  id INT NOT NULL AUTO_INCREMENT,
  name VARCHAR(15),
  surname VARCHAR(25),
  department VARCHAR(20),
  salary INT,
  PRIMARY KEY (id)
);
```
(Optional) Add test data
```sql
INSERT INTO employees (name, surname, department, salary) VALUES
('Lucas', 'Neumann', 'IT', 1200),
('Sophie', 'Keller', 'HR', 900),
('Maria', 'Klein', 'Sales', 950);
```

✅ Database is ready.


### 5️⃣ Configure database credentials (Server)

Open the configuration file:

```markdown
src/main/resources/application.properties
```

Update credentials:

```java
spring.datasource.url=jdbc:mysql://localhost:3306/my_db?useSSL=false
spring.datasource.username=bestuser
spring.datasource.password=bestuser
```

You can change the following properties:

spring.datasource.url → database name and connection URL

spring.datasource.username → MySQL username

spring.datasource.password → MySQL password


Make sure the database name matches the one created in MySQL.


### 6️⃣ Run the Application (Main class SpringBootRestApplication)

Run main class:
```markdown
SpringbootRestApplication.java
```
### 7️⃣ Test API in browser or Postman

Base URL:
```url
http://localhost:3333/springboot_rest/api/employees
```

### 📡 API Endpoints
| Method | Endpoint             | Description        |
|--------|----------------------|--------------------|
| GET    | /api/employees       | Get all employees  |
| GET    | /api/employees/{id}  | Get employee by ID |
| POST   | /api/employees       | Create new employee|
| PUT    | /api/employees       | Update employee    |
| DELETE | /api/employees/{id}  | Delete employee    |
| GET    | /api/employees/name/{name}| Get employees by name|


### 🧪 Example JSON
Create employee (POST)
```json
{
  "name": "Jonas",
  "surname": "Richter",
  "department": "Sales",
  "salary": 1600
}
```
Update employee (PUT)
```json
{
  "id": 1,
  "name": "Jonas",
  "surname": "Richter",
  "department": "Sales",
  "salary": 1600
}
```
## ⚙️ Technologies Used

- Spring Boot
- Spring MVC (REST)
- Spring Data JPA
- Hibernate
- MySQL
- Maven

## ℹ️ Important Notes

- Backend-focused REST API with JSON-based communication
- Persistence layer implemented using Spring Data JPA repositories
- Repository pattern replaces manual DAO implementation
- API can be tested using Postman or any HTTP client
- Database is configured externally and should be created locally

🎯 Learning Goals

This project demonstrates:
- How Spring Data JPA simplifies data access
- Difference between DAO and Repository approaches
- Automatic query generation by method names
- CRUD operations using JpaRepository
- Clean layered architecture in Spring Boot
