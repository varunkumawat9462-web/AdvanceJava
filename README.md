# Advanced Java Programming Laboratory (ADJ Lab)

A comprehensive collection of **Advanced Java Programming** laboratory practicals and projects, arranged chronologically from **Experiment 1 to the final Capstone Project**.

---

## 📋 Table of Contents


- [Index of Experiments](#-index-of-experiments)
- [Prerequisites & System Setup](#-prerequisites--system-setup)
- [Experiment 1: GUI Form Development using Java Swing](#-experiment-1-gui-form-development-using-java-swing)
- [Experiment 2: Model-View-Controller (MVC) Architecture](#-experiment-2-model-view-controller-mvc-architecture)
- [Experiment 3: TCP Socket Programming (Client-Server Communication)](#-experiment-3-tcp-socket-programming-client-server-communication)
- [Experiment 4: Java Database Connectivity (JDBC) CRUD Operations](#-experiment-4-java-database-connectivity-jdbc-crud-operations)
- [Experiment 5: Remote Method Invocation (Java RMI Distributed Computing)](#-experiment-6-remote-method-invocation-java-rmi-distributed-computing)
- [Experiment 6: Web Server Environment Setup & Application Deployment (Apache Tomcat)](#-experiment-7-web-server-environment-setup--application-deployment-apache-tomcat)
- project : Shopsphere project for an e commerce platform
---

## 📑 Index of Experiments

| Exp No. | Experiment Title | Core Technologies | Directory |
|:---:|---|---|---|
| **01** | **Student Registration GUI Form** | Java Swing, AWT, Event Handling | [`exp1/`](exp1/) |
| **02** | **MVC Pattern Calculator Application** | Java Swing, MVC Architecture | [`calc/`](calc/) |
| **03** | **TCP Socket Client-Server Echo System** | Java Networking (`java.net`), Sockets, I/O Streams | [`server-client/`](server-client/) |
| **04** | **Database Connectivity & SQL Operations (JDBC)** | JDBC 4.2, MySQL, PreparedStatements | [`jdbc/exp3/`](jdbc/exp3/) |
| **05** | **Distributed Computing via Java RMI** | Java RMI, Remote Interfaces, RMI Registry | [`Remote-Method-Invocation/`](Remote-Method-Invocation/) |
| **06** | **Servlet Container & Web Server Deployment** | Apache Tomcat 9, WAR Deployment, Web XML | [`apache-tomcat-9.0.121/`](apache-tomcat-9.0.121/) |
| **07** | **ShopSphere project** | Jakarta Servlets + JSP/JSTL + JDBC (HikariCP) + MySQL, | [`ShopSphere/`](ShopSphere/) |
---

## 🛠️ Prerequisites & System Setup

Ensure the following tools and runtimes are installed on your workstation:

1. **Java Development Kit (JDK 17 or 21+):**
   ```bash
   java -version
   javac -version
   ```
2. **MySQL Database Server (8.0+):**
   ```bash
   mysql --version
   ```
3. **Apache Maven (3.8+):**
   ```bash
   mvn -version
   ```
4. **Apache Tomcat Server (9.0.x or 10.1+/11.0.x):**
   Bundled inside [`apache-tomcat-9.0.121/`](apache-tomcat-9.0.121/) for Servlet development.

---

## 🧪 Experiment 1: GUI Form Development using Java Swing

### 🎯 Aim & Objective
To design and implement an interactive desktop Graphical User Interface (GUI) for a **Student Registration Form** using Java Swing components and event listeners.

### 📂 Directory & File Structure
```
exp1/
├── StudentRegistration.java    # Swing GUI class with ActionListener
└── StudentRegistration.class   # Compiled bytecode
```

### 💡 Key Concepts & Implementation Details
- **Components Used**: `JFrame`, `JLabel`, `JTextField`, `JRadioButton`, `ButtonGroup`, `JCheckBox`, `JButton`.
- **Layout Management**: Absolute positioning with `setLayout(null)` and `setBounds(x, y, width, height)`.
- **Event Handling**: Implements `ActionListener` to capture button clicks on **Submit** and **Reset**.
- **User Validation**: Validates required fields and terms acceptance, rendering user details via `JOptionPane.showMessageDialog()`.

### 🚀 Compilation & Execution
```bash
# Navigate to experiment directory
cd exp1

# Compile
javac StudentRegistration.java

# Run
java StudentRegistration
```

---

## 🧪 Experiment 2: Model-View-Controller (MVC) Architecture

### 🎯 Aim & Objective
To design and implement an interactive desktop Calculator adhering strictly to the **Model-View-Controller (MVC)** architectural design pattern, separating business logic, user interface, and event handling.

### 📂 Directory & File Structure
```
calc/
├── ModelsCalculator.java       # Model: Contains arithmetic calculation logic
├── ViewsCalculator.java        # View: Builds Swing GUI components & layouts
├── ControllerCalculator.java   # Controller: Binds View events to Model methods
├── Runmain.java                # Application Entry Point
└── README.md                   # Module documentation
```

### 💡 Key Concepts & Implementation Details
- **Model (`ModelsCalculator`)**: Encapsulates arithmetic operations (`add`, `sub`, `multiply`, `divide`) and edge-case handling (e.g. division by zero).
- **View (`ViewsCalculator`)**: Constructs the UI with `JTextField` for input/display and operator buttons (`+`, `-`, `*`, `/`).
- **Controller (`ControllerCalculator`)**: Attaches action listeners to the view buttons, parses inputs, triggers Model operations, and updates the view display.
- **Benefits**: Loose coupling, high maintainability, and clean code separation.

### 🚀 Compilation & Execution
```bash
# Navigate to experiment directory
cd calc

# Compile all source files
javac *.java

# Launch application
java Runmain
```

---

## 🧪 Experiment 3: TCP Socket Programming (Client-Server Communication)

### 🎯 Aim & Objective
To implement two-way network communication over a TCP connection using Java Sockets (`java.net` package) with a dedicated Server and Client echo protocol.

### 📂 Directory & File Structure
```
server-client/
├── server.java     # TCP Server listening on port 5000
└── client.java     # TCP Client connecting to localhost:5000
```

### 💡 Key Concepts & Implementation Details
- **TCP Socket Architecture**: Utilizes `ServerSocket` on port `5000` to listen for incoming connections and `Socket` to establish client-server streams.
- **I/O Streams**: Uses `BufferedReader` wrapping `InputStreamReader` for receiving messages and `PrintWriter` with auto-flush for sending text over the stream.
- **Communication Protocol**:
  - The server echoes every message back with an `"Echo: <message>"` prefix.
  - Graceful disconnection protocol when the client transmits `"bye"`.

### 🚀 Compilation & Execution
Open two terminal windows:

```bash
# Compile both programs
cd server-client
javac server.java client.java

# Terminal 1: Start Server
java server

# Terminal 2: Start Client
java client
```

---

## 🧪 Experiment 4: Java Database Connectivity (JDBC) CRUD Operations

### 🎯 Aim & Objective
To establish a connection between a Java program and a MySQL relational database using JDBC (Type-4 Driver), execute parameterized queries, and perform basic CRUD operations.

### 📂 Directory & File Structure
```
jdbc/exp3/
├── lib/
│   └── mysql-connector-j-26.7.0.jar   # MySQL JDBC Driver library
├── src/
│   └── Main.java                      # JDBC connection, insert & query execution
├── bin/                               # Compiled classes
└── README.md                          # Configuration notes
```

### 💡 Key Concepts & Implementation Details
- **Driver Registration**: Loading the MySQL driver class `Class.forName("com.mysql.cj.jdbc.Driver")`.
- **Connection Management**: Connecting via `DriverManager.getConnection(url, user, password)`.
- **Parameterized SQL with `PreparedStatement`**: Safe query execution for inserting student records into the database.
- **Data Retrieval with `Statement` & `ResultSet`**: Executing `SELECT` queries and reading result records via cursor traversal (`rs.next()`).

### 🗄️ Database Setup
```sql
CREATE DATABASE IF NOT EXISTS collage_db;
USE collage_db;

CREATE TABLE IF NOT EXISTS Student (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    branch VARCHAR(50)
);
```

### 🚀 Compilation & Execution
```bash
cd jdbc/exp3

# Compile with JDBC Driver in classpath
javac -cp "lib/*:src" src/Main.java -d bin

# Run program
java -cp "lib/*:bin" Main
```

---

## 🧪 Experiment 5: Remote Method Invocation (Java RMI Distributed Computing)

### 🎯 Aim & Objective
To build a distributed client-server application using Java Remote Method Invocation (RMI), allowing a remote client to execute object methods hosted on a remote server.

### 📂 Directory & File Structure
```
Remote-Method-Invocation/
├── Calculator.java         # Remote Interface (extends java.rmi.Remote)
├── CalculatorImpl.java     # Remote Implementation (extends UnicastRemoteObject)
├── Server.java             # RMI Server (binds service to RMI Registry)
└── client.java             # RMI Client (performs lookup and calls remote methods)
```

### 💡 Key Concepts & Implementation Details
- **Remote Interface (`Calculator`)**: Declares remote methods (`add`, `subtract`) throwing `RemoteException`.
- **Remote Implementation (`CalculatorImpl`)**: Extends `UnicastRemoteObject` to export the object for remote communication.
- **RMI Registry & Binding**: `Server` creates the implementation and registers it via `Naming.rebind("rmi://localhost/CalculatorService", calc)`.
- **Client Lookup & Invocation**: `client` resolves the remote stub via `Naming.lookup(...)` and transparently invokes arithmetic operations across JVMs.

### 🚀 Compilation & Execution
```bash
cd Remote-Method-Invocation

# Compile all RMI files
javac *.java

# Start RMI Registry (if not embedded)
rmiregistry &

# Terminal 1: Start RMI Server
java Server

# Terminal 2: Run RMI Client
java client
```

---

## 🧪 Experiment 6: Web Server Environment Setup & Application Deployment (Apache Tomcat)

### 🎯 Aim & Objective
To configure and manage an enterprise Java Servlet Container and Web Server (**Apache Tomcat 9**), understand the container directory structure, configure deployment descriptors, and deploy web applications.

### 📂 Directory & File Structure
```
apache-tomcat-9.0.121/
├── bin/                    # Server lifecycle scripts (startup.sh, shutdown.sh, catalina.sh)
├── conf/                   # Configuration files (server.xml, web.xml, context.xml)
├── lib/                    # Servlet API & container libraries (servlet-api.jar, jsp-api.jar)
├── logs/                   # Catalina and access log files
├── webapps/                # Deployment folder for web applications
│   ├── myWebapp/           # Static and dynamic test webapp
│   └── servlet-1.0-SNAPSHOT.war # Deployed Web Archive
└── work/                   # Compiled JSP servlets and temporary runtime files
```

### 💡 Key Concepts & Implementation Details
- **Servlet Container Lifecycle**: Starting, stopping, and inspecting server logs.
- **Port & Connector Configuration**: Configuring HTTP connectors in `conf/server.xml` (default port `8080`).
- **WAR Deployment**: Automated unpacking and deployment of Web Application Archives in `webapps/`.

### 🚀 Running the Tomcat Server
```bash
cd apache-tomcat-9.0.121/bin

# Ensure scripts have execute permissions
chmod +x *.sh

# Start Tomcat Server
./startup.sh

# Open browser: http://localhost:8080/

# Stop Tomcat Server
./shutdown.sh
```


## 👨‍💻 Repository Author

- **Author**: Varun Kumawat
- **Course**: Advanced Java Laboratory 
