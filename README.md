# Employee Management REST API

A RESTful backend application built with **Java, Spring Boot, Spring Data JPA, and MySQL** to manage employee information through CRUD (Create, Read, Update, Delete) operations.

## About the Project

The Employee Management REST API is a backend application that allows clients to create, retrieve, update, and delete employee records using HTTP requests.

It demonstrates the fundamentals of REST API development, database integration, request validation, exception handling, and layered application architecture using Spring Boot.

## Features

- Create new employee records
- Retrieve all employees
- Retrieve an employee by ID
- Update existing employee details
- Delete an employee record
- Validate employee input fields
- Validate email format and salary constraints
- Handle employee-not-found exceptions
- Store employee data in MySQL
- Use Spring Data JPA for database operations

## Tech Stack

| Technology | Purpose |
|---|---|
| Java | Backend programming |
| Spring Boot | Application framework |
| Spring Web MVC | REST API endpoints |
| Spring Data JPA | Database access |
| Hibernate | Object-relational mapping |
| MySQL | Relational database |
| Maven | Dependency and build management |
| Jakarta Validation | Input validation |
| Git | Version control |
| GitHub | Source code hosting |
| Visual Studio Code | Development environment |

## Project Structure

```text
employee-management/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/employee_management/
│   │   │       ├── Employee.java
│   │   │       ├── EmployeeController.java
│   │   │       ├── EmployeeManagementApplication.java
│   │   │       ├── EmployeeNotFoundException.java
│   │   │       ├── EmployeeRepository.java
│   │   │       ├── EmployeeService.java
│   │   │       └── GlobalExceptionHandler.java
│   │   └── resources/
│   │       └── application.properties
│   └── test/
├── mvnw
├── mvnw.cmd
├── pom.xml
├── .gitignore
└── README.md
```

## Prerequisites

Install the following software:

- Java Development Kit (JDK)
- MySQL Server
- Git
- Visual Studio Code or another Java IDE
- MySQL Workbench (optional)

## Database Setup

Create the database in MySQL:

```sql
CREATE DATABASE employee_db;
```

Configure the connection in `src/main/resources/application.properties`:

```properties
spring.application.name=employee-management

spring.datasource.url=jdbc:mysql://localhost:3306/employee_db
spring.datasource.username=root
spring.datasource.password=${DB_PASSWORD}
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.open-in-view=false
```

Set `DB_PASSWORD` to your own MySQL password before starting the application. Never commit database passwords or other secrets to GitHub.

## Run the Application

### 1. Clone the repository

Replace `YOUR-USERNAME` with your GitHub username.

```bash
git clone https://github.com/YOUR-USERNAME/employee-management-rest-api.git
```

### 2. Open the project directory

```bash
cd employee-management-rest-api
```

### 3. Configure the database password

In Windows PowerShell:

```powershell
$env:DB_PASSWORD = Read-Host "Enter your MySQL password"
```

Keep this terminal open while running the application.

### 4. Start Spring Boot

On Windows:

```powershell
.\mvnw.cmd spring-boot:run
```

On macOS or Linux:

```bash
./mvnw spring-boot:run
```

After successful startup, the application normally runs at:

`http://localhost:8080`

## REST API Endpoints

Base URL: `http://localhost:8080/api/employees`

| HTTP Method | Endpoint | Description |
|---|---|---|
| POST | `/api/employees` | Create an employee |
| GET | `/api/employees` | Retrieve all employees |
| GET | `/api/employees/{id}` | Retrieve an employee by ID |
| PUT | `/api/employees/{id}` | Update an employee |
| DELETE | `/api/employees/{id}` | Delete an employee |

## API Usage Examples

### Create an Employee

**Method:** `POST`

**Endpoint:** `/api/employees`

Request header:

`Content-Type: application/json`

Request body:

```json
{
  "name": "Ravi Kumar",
  "email": "ravi@example.com",
  "department": "IT",
  "salary": 40000.00
}
```

### Retrieve All Employees

```http
GET /api/employees
```

### Retrieve an Employee by ID

```http
GET /api/employees/1
```

### Update an Employee

```http
PUT /api/employees/1
```

Request body:

```json
{
  "name": "Ravi Kumar",
  "email": "ravi@example.com",
  "department": "Finance",
  "salary": 45000.00
}
```

### Delete an Employee

```http
DELETE /api/employees/1
```

Use an existing employee ID when testing update and delete requests.

## Employee Data Model

| Field | Description |
|---|---|
| `id` | Automatically generated employee ID |
| `name` | Employee name |
| `email` | Employee email address; must be unique |
| `department` | Employee department |
| `salary` | Employee salary |

The application applies validation rules to required fields, email format, and salary values.

## Testing

You can test the API using PowerShell or an API client such as Postman.

Recommended tests:

- Create an employee with valid data
- Retrieve all employees
- Retrieve an existing employee by ID
- Update an employee
- Delete an employee
- Submit invalid email or missing required fields
- Request an employee ID that does not exist
- Try creating an employee with a duplicate email

## Learning Outcomes

This project provides practical experience with:

- Java backend development
- RESTful API design
- Spring Boot application development
- Controller, service, repository, and entity layers
- MySQL database connectivity
- CRUD operations with Spring Data JPA
- Input validation and exception handling
- Maven and Git workflows

## Future Enhancements

- Add pagination and sorting
- Implement employee search and department filtering
- Add authentication and authorization
- Write unit and integration tests
- Integrate Swagger/OpenAPI documentation
- Develop a frontend application

## Author

**Your Name**

GitHub: https://github.com/YOUR-USERNAME

## License

This project is intended for learning and educational purposes. Add a license file if you choose to publish the project under a specific open-source license.
