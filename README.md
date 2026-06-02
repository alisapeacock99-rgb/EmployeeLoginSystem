# Employee Login & Registration System

## Overview

The Employee Login & Registration System is a Java web application developed using JSP, Servlets, and PostgreSQL. It provides a secure platform for employee registration, authentication, and session-based access control.

The application allows employees to create an account, log in using their credentials, access a personalized dashboard, and securely log out. Database connectivity is handled through JDBC with PostgreSQL, while user sessions are managed using Jakarta Servlet sessions.

---

## Features

* Employee registration with personal and work-related information
* Secure employee login authentication
* Session-based user management
* Personalized dashboard after successful login
* Logout functionality
* PostgreSQL database integration
* Responsive and modern user interface using HTML, CSS, and JSP

---

## Technologies Used

### Backend

* Java
* Jakarta Servlets
* JDBC

### Frontend

* JSP (Java Server Pages)
* HTML5
* CSS3

### Database

* PostgreSQL

### Development Tools

* Apache Tomcat
* NetBeans IDE

---

## System Workflow

### Employee Registration

1. Employee enters:

   * Employee ID
   * Full Name
   * Department
   * Role
   * Password
   * Phone Number
   * Email Address

2. Registration data is stored in the PostgreSQL database.

3. User is redirected to the login page after successful registration.

### Employee Login

1. Employee enters:

   * Employee ID
   * Password

2. Credentials are validated against the database.

3. Upon successful authentication:

   * A session is created.
   * Employee name is stored in the session.
   * User is redirected to the dashboard.

### Dashboard Access

* Only authenticated users can access the dashboard.
* Unauthorized users are automatically redirected to the login page.

### Logout

* User session is invalidated.
* User is redirected to the login page.

---

## Project Structure

```text
EmployeeLoginSystem/
│
├── src/
│   ├── java/
│   │   ├── Servlet/
│   │   │   ├── LoginServlet.java
│   │   │   ├── RegisterServlet.java
│   │   │   └── LogoutServlet.java
│   │   │
│   │   └── database/
│   │       ├── DBConnection.java
│   │       └── TestConnection.java
│   │
│   └── db.properties
│
├── web/
│   ├── index.jsp
│   ├── register.jsp
│   ├── login.jsp
│   └── dashboard.jsp
│
└── build.xml
```

---

## Database Configuration

The application uses a PostgreSQL database connection configured through the `db.properties` file.

Example:

```properties
db.url=jdbc:postgresql://localhost:5432/employee_system
db.username=your_username
db.password=your_password
```

---

## Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/EmployeeLoginSystem.git
```

### 2. Create PostgreSQL Database

```sql
CREATE DATABASE employee_system;
```

### 3. Create Employee Table

```sql
CREATE TABLE employee (
    employee_id VARCHAR(20) PRIMARY KEY,
    full_name VARCHAR(100),
    department VARCHAR(100),
    role VARCHAR(100),
    password VARCHAR(100),
    phone VARCHAR(20),
    email VARCHAR(100)
);
```

### 4. Create Login Table

```sql
CREATE TABLE login (
    employee_id VARCHAR(20),
    password VARCHAR(100)
);
```

### 5. Configure Database Credentials

Update the `db.properties` file with your PostgreSQL credentials.

### 6. Deploy the Project

* Open the project in NetBeans IDE.
* Configure Apache Tomcat.
* Build and run the project.

---

## Future Enhancements

* Password hashing using BCrypt
* Role-based access control (Admin/Employee)
* Employee profile management
* Password reset functionality
* Email verification
* CRUD operations for employee records
* Enhanced security and validation
* REST API integration

---

## Author
-> Alisa Peacock 
Developed as a Java Web Application project to demonstrate authentication, session management, JDBC database connectivity, and MVC-based web development using JSP, Servlets, and PostgreSQL.
