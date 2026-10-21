# Advanced Java Programming — Laboratory Work

This repository contains practical implementations developed as part of the Advanced Java Programming laboratory. The exercises cover desktop GUI development, software architecture, network communication, database connectivity, distributed applications, and web server deployment.

The repository also includes **ShopSphere**, an e-commerce application project.

## Contents

- [Project Overview](#project-overview)
- [Software Requirements](#software-requirements)
- [Laboratory Exercises](#laboratory-exercises)
- [ShopSphere Application](#shopsphere-application)
- [Setup and Execution](#setup-and-execution)
- [Learning Outcomes](#learning-outcomes)

---

## Project Overview

The purpose of this repository is to practice Java programming concepts through small, focused applications. Each exercise demonstrates a different aspect of Java application development, from building graphical interfaces to connecting applications with databases and remote services.

## Software Requirements

Install the following software before running the practical programs:

| Software | Purpose |
|---|---|
| JDK 17 or later | Compiling and executing Java programs |
| MySQL Server 8.0+ | Relational database operations |
| Apache Maven 3.8+ | Managing Java project dependencies |
| Apache Tomcat | Running Java web applications |
| Git | Source code management |

Verify your Java installation with:

```bash
java -version
javac -version
```

Check Maven with:

```bash
mvn -version
```

---

## Laboratory Exercises

### Exercise 1 — Student Registration Form

**Technologies:** Java Swing, AWT, Event Handling

A desktop application that provides a form for entering student information.

**Topics covered**
- Creating windows and form components using Swing.
- Arranging labels, text fields, buttons, and selection controls.
- Handling user actions through event listeners.
- Validating form input and displaying messages.

**Location:** `exp1/`

**Run the application**

```bash
cd exp1
javac StudentRegistration.java
java StudentRegistration
```

### Exercise 2 — Calculator Using MVC Architecture

**Technologies:** Java Swing, Model-View-Controller

This exercise implements a calculator with separate classes for the user interface, calculation logic, and event handling.

**Main components**
- `ModelsCalculator.java` — arithmetic operations.
- `ViewsCalculator.java` — graphical interface.
- `ControllerCalculator.java` — connects user actions to calculations.
- `Runmain.java` — starts the application.

**Topics covered**
- Separation of application responsibilities.
- Handling calculator button events.
- Performing arithmetic operations.
- Improving code organization through MVC.

**Location:** `calc/`

**Run the application**

```bash
cd calc
javac *.java
java Runmain
```

### Exercise 3 — TCP Client-Server Communication

**Technologies:** Java Networking, TCP Sockets, I/O Streams

A client and server communicate over a TCP connection. The server returns a response for each message received from the client.

**Main files**
- `server.java` — accepts client connections on port 5000.
- `client.java` — connects to the server and exchanges messages.

**Topics covered**
- Creating server and client sockets.
- Reading and sending data through streams.
- Implementing a basic message-response protocol.
- Closing the communication session using a termination message.

**Location:** `server-client/`

**Run the application**

Compile both programs:

```bash
cd server-client
javac server.java client.java
```

Open two terminals in the same directory.

Terminal 1:

```bash
java server
```

Terminal 2:

```bash
java client
```

### Exercise 4 — Database Operations with JDBC

**Technologies:** JDBC, MySQL, SQL, PreparedStatement

This practical demonstrates how a Java application connects to MySQL and performs database operations on student records.

**Topics covered**
- Establishing database connections.
- Executing SQL queries.
- Inserting records using `PreparedStatement`.
- Retrieving results using `ResultSet`.

**Location:** `jdbc/exp3/`

**Database preparation**

Execute the following SQL statements in MySQL:

```sql
CREATE DATABASE IF NOT EXISTS collage_db;
USE collage_db;

CREATE TABLE IF NOT EXISTS Student (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    branch VARCHAR(50)
);
```

Configure the database URL, username, and password in the Java program as required.

**Compile and run**

```bash
cd jdbc/exp3
javac -cp "lib/*;src" -d bin src/Main.java
java -cp "lib/*;bin" Main
```

The classpath separator shown above is for Windows. On Linux or macOS, use `:` instead of `;`.

### Exercise 5 — Remote Method Invocation (RMI)

**Technologies:** Java RMI, Remote Interfaces, Distributed Computing

This exercise demonstrates how a client can invoke methods on an object running in another Java process through Remote Method Invocation.

**Main files**
- `Calculator.java` — declares the remote operations.
- `CalculatorImpl.java` — implements the remote interface.
- `Server.java` — registers and exposes the service.
- `client.java` — locates the remote service and calls its methods.

**Topics covered**
- Defining remote interfaces.
- Implementing remote objects.
- Registering services with the RMI Registry.
- Invoking methods from a client application.

**Location:** `Remote-Method-Invocation/`

**Compile the source files**

```bash
cd Remote-Method-Invocation
javac *.java
```

Start the RMI Registry if it is not started by the server program:

```bash
rmiregistry
```

In separate terminals, start the server and then the client:

```bash
java Server
```

```bash
java client
```

### Exercise 6 — Apache Tomcat Setup and Deployment

**Technologies:** Apache Tomcat, Java Servlets, WAR Deployment

This exercise focuses on configuring a servlet container and understanding how Java web applications are deployed.

**Topics covered**
- Exploring Tomcat configuration and library directories.
- Starting and stopping the server.
- Understanding the HTTP connector and port configuration.
- Deploying web applications through WAR files.

**Location:** `apache-tomcat-9.0.121/`

**Start Tomcat on Linux or macOS**

```bash
cd apache-tomcat-9.0.121/bin
chmod +x *.sh
./startup.sh
```

Open `http://localhost:8080/` in your browser.

To stop the server:

```bash
./shutdown.sh
```

On Windows, use the appropriate `.bat` scripts in the `bin` directory.

---

## ShopSphere Application

**Technologies:** Jakarta Servlets, JSP/JSTL, JDBC, HikariCP, MySQL

ShopSphere is an e-commerce application included in this repository. It extends the practical work into a larger web application that uses Java-based server-side technologies and database connectivity.

**Project directory:** `ShopSphere/`

Refer to the project's own documentation and configuration files for its specific setup instructions, database schema, and execution steps.

---

## Setup and Execution

1. Clone or download the repository.
2. Install the required Java development tools and any dependencies needed by the selected exercise.
3. Open a terminal in the relevant project directory.
4. Configure database credentials or server settings where required.
5. Compile and execute the program using the commands provided in its section.

Some exercises require a running MySQL server, an available network port, or an active Tomcat or RMI service.

## Learning Outcomes

Through these exercises, the laboratory work provides practice in:

- Developing desktop applications with Java Swing.
- Applying MVC architecture to separate application logic.
- Building TCP-based client-server programs.
- Connecting Java applications to relational databases.
- Understanding distributed applications using Java RMI.
- Deploying Java web applications on Apache Tomcat.
- Combining Java web technologies in a larger project.

---

*Advanced Java Programming Laboratory — Practical Work and Project Documentation*
