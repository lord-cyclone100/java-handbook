<h1>Using database in Java (JDBC Basics)

<h2> ✅Overview</h2>

<p>JDBC (Java Database Connectivity) is a standard Java API that enables Java applications to interact with relational databases using SQL. It provides a platform-independent way to connect, query, and manage data stored in databases like MySQL, Oracle, PostgreSQL, and others.</p>

<h2>🗃️ What is a Database?</h2>

<p>A database is an organized collection of data that is stored and accessed electronically. Databases are used to store information such as user records, transaction details, inventory, and more in a structured way, typically using tables.</p>

<p>🔹 Types of Databases</p>

| Type	| Description |
| ------- | ----------- |
| Relational DB |	Stores data in rows and columns (tables). Uses SQL. E.g., MySQL, Oracle, PostgreSQL
| NoSQL DB	| Stores data as documents, key-value pairs, or graphs. E.g., MongoDB, Redis

<h2>💡 Why Use a Database?</h2>

- To store and retrieve data efficiently.
- To ensure data consistency, integrity, and security.
- To manage large volumes of data in a scalable way.
- To support multi-user access and concurrent data operations.

<h2>☕ How Java Handles Databases</h2>

<p>Java uses the JDBC API (Java Database Connectivity) to connect and interact with relational databases like MySQL, Oracle, and PostgreSQL.</p>

<h2>🔗 Java-Database Connection Flow:</h2>

- Java application uses JDBC API to connect to a database.
- JDBC communicates through a JDBC Driver specific to the database (e.g., MySQL driver).
- SQL queries are sent to the database via Statements or PreparedStatements.
- Results from the database (like tables) are returned as ResultSet objects.
- Java code reads, updates, or deletes data based on the response.

<h3>🧭 Java + Database = Seamless Integration</h3>

Java acts like a bridge between the user interface (UI) and the database. Here's a simplified view:

> User (UI) → Java Code → JDBC → Database → Data → JDBC → Java Code → User

<h2>🔧 Key Tools for Java Database Handling</h2>

| Tool/Concept | Role |
|--------------|------|
| DriverManager |	Loads database drivers and manages connection requests |
| Connection	| Represents the link between Java and the database |
| Statement / PreparedStatement	| Executes SQL queries |
| ResultSet	| Holds results returned from SELECT queries |
| SQL	| Language used to define and manipulate data in relational databases |

<h3>📦 Example Use-Cases</h3>

+ Login/Signup systems (storing user credentials)
+ Library Management System (books, members, loans)
+ Online Shopping Cart (products, customers, orders)
+ Student Result Portal (marks, attendance, reports)


<h1> 🔍Core Concepts</h1>

| Component	| Description |
| --------- | ----------- |
| JDBC Driver |	Translates Java calls to DB-specific calls. E.g., MySQL Connector/J. |
| DriverManager |	Manages the set of JDBC drivers. |
| Connection |	Establishes a session with the database. |
| Statement |	Used to execute SQL queries. |
| PreparedStatement |	A safer version of Statement to prevent SQL injection. |
| ResultSet |	Holds data retrieved from the database after executing a query. |
| SQLException |	Handles SQL errors and issues. |


<h2>🛠️ Applications of JDBC</h2>

- Web and desktop applications (login, registration, data entry)
- Enterprise back-end systems
- Reporting and analytics tools
- Data migration and ETL
- IoT or embedded systems with database access

<h2>🔗 JDBC Workflow </h2>

1. Load JDBC Driver
2. Establish Database Connection
3. Create Statement or PreparedStatement
4. Execute SQL Query
5. Process Results (ResultSet)
6. Close Connection

<h2>📁 Sample Database (MySQL)</h2>

```sql
CREATE DATABASE testdb;
USE testdb;

CREATE TABLE users (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100)
);

INSERT INTO users VALUES
(1, 'Alice', 'alice@example.com'),
(2, 'Bob', 'bob@example.com');
```


<h2>JDBC Example (Using Eclipse IDE)</h2>

📌 Step-by-Step

1. Create Java Project
    - In Eclipse → File > New > Java Project → Name: JDBCExample
2. Add JDBC Driver
    - Right-click project → Build Path > Configure Build Path > Libraries > Add External JARs
    - Add mysql-connector-java-8.x.x.jar
3. Write the Code

```java
import java.sql.*;

public class JDBCExample {
    public static void main(String[] args) {
        String url = "jdbc:mysql://localhost:3306/testdb";
        String user = "root";
        String password = "yourpassword";

        try {
            // Step 1: Load JDBC Driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // Step 2: Establish Connection
            Connection conn = DriverManager.getConnection(url, user, password);

            // Step 3: Create Statement
            Statement stmt = conn.createStatement();

            // Step 4: Execute SQL Query
            ResultSet rs = stmt.executeQuery("SELECT * FROM users");

            // Step 5: Process Results
            while (rs.next()) {
                int id = rs.getInt("id");
                String name = rs.getString("name");
                String email = rs.getString("email");

                System.out.println(id + " | " + name + " | " + email);
            }

            // Step 6: Close Everything
            rs.close();
            stmt.close();
            conn.close();

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

<h2>🛡️ Best Practices</h2>

+ ✅ Use PreparedStatement for dynamic SQL to prevent SQL injection.
+ ✅ Use try-with-resources to auto-close connections.
+ ✅ Handle exceptions using proper logging or error handling.
+ ✅ Never hardcode credentials in production.

<h2>⚡ Alternative: PreparedStatement Example</h2>

```java
String sql = "SELECT * FROM users WHERE id = ?";
PreparedStatement pstmt = conn.prepareStatement(sql);
pstmt.setInt(1, 1);
ResultSet rs = pstmt.executeQuery();
```

<h1>📚 Summary</h1>

+ JDBC is crucial for data-driven applications.
+ Use Statement for static SQL, PreparedStatement for dynamic, secure queries.
+ Use Eclipse for easy project creation and driver management.