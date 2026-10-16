# Hibernate Operations with Java and MySQL

A hands-on Java project demonstrating database operations using Hibernate ORM and MySQL. This repository covers the fundamental Create, Read, Update, and Delete (CRUD) operations for managing student records, along with primary key configuration and database connectivity.

## Project Overview

Hibernate is an Object-Relational Mapping (ORM) framework for Java that simplifies database interactions by mapping Java objects to relational database tables.

This project demonstrates how to configure Hibernate, establish database connectivity, map a Java entity to a database table, and perform common database operations without writing repetitive JDBC code for every operation.

The project uses a student entity as an example to illustrate how Java applications interact with a MySQL database through Hibernate.

## Project Objectives

- Understand the fundamentals of Hibernate ORM.
- Configure Hibernate to connect to a MySQL database.
- Map Java classes to relational database tables.
- Perform Create, Read, Update, and Delete operations on student records.
- Understand primary key configuration and entity identification.
- Execute database queries using Hibernate.
- Explore the relationship between Java objects, Hibernate, and relational databases.

## Technologies and Tools

| Technology | Purpose |
|---|---|
| Java | Application development |
| Hibernate ORM | Object-relational mapping and persistence |
| MySQL | Relational database management |
| MySQL Workbench | Database administration and query execution |
| JDBC | Java database connectivity concepts |
| Eclipse IDE | Java development environment |
| XML | Hibernate configuration |

## Repository Structure

```text
Hibernate-operations/
|
├── CreateStudentDemo.java   # Creates a student record
├── ReadStudentDemo.java     # Retrieves student records
├── QueryStudentDemo.java    # Demonstrates student queries
├── UpdateStudentDemo.java  # Updates an existing student record
├── DeleteStudentDemo.java  # Deletes a student record
├── PrimaryKeyDemo.java     # Demonstrates primary key concepts
├── Student.java            # Student entity class
├── TestJdbc.java           # JDBC connectivity example
├── hibernate.cfg.xml       # Hibernate configuration
└── README.md               # Project documentation
```

## Core Concepts Demonstrated

### 1. Create Operation

File: [`CreateStudentDemo.java`](CreateStudentDemo.java)

Demonstrates inserting a new student record into the database using Hibernate.

Key concepts:

- Creating a Hibernate session.
- Beginning and managing a database transaction.
- Persisting a Java object.
- Committing a transaction to save changes.

### 2. Read Operation

File: [`ReadStudentDemo.java`](ReadStudentDemo.java)

Demonstrates retrieving student information from the database.

Key concepts:

- Loading an entity by its identifier.
- Managing Hibernate sessions.
- Retrieving database records as Java objects.
- Handling records that may not exist.

### 3. Query Operations

File: [`QueryStudentDemo.java`](QueryStudentDemo.java)

Demonstrates querying student data using Hibernate.

Key concepts:

- Retrieving records based on query criteria.
- Understanding Hibernate Query Language (HQL), if used in the implementation.
- Mapping query results to Java objects.
- Filtering and retrieving database records.

### 4. Update Operation

File: [`UpdateStudentDemo.java`](UpdateStudentDemo.java)

Demonstrates modifying an existing student record.

Key concepts:

- Retrieving an existing entity.
- Updating entity attributes.
- Managing transactions.
- Persisting changes to the database.

### 5. Delete Operation

File: [`DeleteStudentDemo.java`](DeleteStudentDemo.java)

Demonstrates removing a student record from the database.

Key concepts:

- Identifying the record to delete.
- Loading the entity.
- Removing an entity through Hibernate.
- Committing the transaction.

### 6. Primary Key Configuration

File: [`PrimaryKeyDemo.java`](PrimaryKeyDemo.java)

Explores primary key concepts used to uniquely identify database records.

Key concepts:

- Entity identity.
- Primary key mapping.
- Identifying individual student records.
- Understanding the role of primary keys in ORM.

### 7. Student Entity

File: [`Student.java`](Student.java)

Defines the Java class used to represent student data.

The class serves as the domain model for database operations. Depending on its implementation, it may contain fields representing student attributes, constructors, getters, setters, and Hibernate mapping annotations.

### 8. JDBC Connectivity

File: [`TestJdbc.java`](TestJdbc.java)

Provides an example related to connecting Java applications to a relational database using JDBC.

This example complements the Hibernate demonstrations by introducing the underlying database connectivity concepts.

### 9. Hibernate Configuration

File: [`hibernate.cfg.xml`](hibernate.cfg.xml)

Contains the Hibernate configuration used by the application.

Typical configuration settings include:

- JDBC driver class.
- Database connection URL.
- Database username and password.
- SQL dialect.
- Hibernate mapping declarations.
- Schema generation or validation settings.

The exact properties depend on the configuration in the repository.

## Getting Started

### Prerequisites

Install the following tools before running the examples:

- Java Development Kit (JDK) compatible with the project's Hibernate version.
- Eclipse IDE or another Java IDE.
- MySQL Server.
- MySQL Workbench.
- A compatible Hibernate library and its required dependencies.

### Step 1: Clone the Repository

```bash
git clone https://github.com/akshayKarai/Hibernate-operations.git
```

Navigate to the project directory:

```bash
cd Hibernate-operations
```

### Step 2: Create the MySQL Database

Open MySQL Workbench and create a database for the project.

For example:

```sql
CREATE DATABASE hibernate_demo;
```

The database name should match the database configured in `hibernate.cfg.xml`.

### Step 3: Configure Hibernate

Open `hibernate.cfg.xml` and configure the database connection properties.

Example configuration for a local MySQL database:

```xml
<hibernate-configuration>
    <session-factory>

        <property name="hibernate.connection.driver_class">
            com.mysql.cj.jdbc.Driver
        </property>

        <property name="hibernate.connection.url">
            jdbc:mysql://localhost:3306/hibernate_demo
        </property>

        <property name="hibernate.connection.username">
            YOUR_MYSQL_USERNAME
        </property>

        <property name="hibernate.connection.password">
            YOUR_MYSQL_PASSWORD
        </property>

        <property name="hibernate.show_sql">true</property>

    </session-factory>
</hibernate-configuration>
```

This is an illustrative configuration. Verify the Hibernate version, database dialect requirements, and entity mappings before using it with the existing source files.

Do not commit real database credentials to a public repository.

### Step 4: Configure the Java Project

1. Import the repository into Eclipse as a Java project.
2. Configure the appropriate JDK.
3. Add the Hibernate libraries and required dependencies to the classpath.
4. Add the MySQL JDBC driver.
5. Verify that `hibernate.cfg.xml` is available on the application's classpath.

If the project does not include a Maven or Gradle build file, the required dependencies must be configured manually or added through a build tool.

### Step 5: Run the Examples

Run the relevant Java classes individually from Eclipse:

1. `CreateStudentDemo.java`
2. `ReadStudentDemo.java`
3. `QueryStudentDemo.java`
4. `UpdateStudentDemo.java`
5. `DeleteStudentDemo.java`
6. `PrimaryKeyDemo.java`

Ensure that the database schema, student entity mapping, and configuration match the source code before running the examples.

Verify the results in MySQL Workbench after each operation.

## Typical CRUD Workflow

| Operation | Hibernate purpose | Expected result |
|---|---|---|
| Create | Save a new entity | A student record is inserted |
| Read | Retrieve an entity | Student details are returned |
| Query | Search for matching records | Matching student records are returned |
| Update | Modify an entity | Existing student data is changed |
| Delete | Remove an entity | The selected student record is deleted |

## Hibernate and JDBC

Hibernate and JDBC both support database access, but they operate at different abstraction levels.

| Feature | JDBC | Hibernate |
|---|---|---|
| Abstraction | Low-level database access | Object-relational mapping |
| SQL handling | Typically written explicitly | Can generate SQL from entity operations |
| Object mapping | Usually handled manually | Supported through entity mappings |
| Persistence context | Not provided by JDBC itself | Managed through Hibernate sessions |
| Transactions | Managed through JDBC connections | Managed through Hibernate and the underlying transaction mechanism |

Hibernate uses JDBC internally to communicate with relational databases. Understanding both technologies helps developers troubleshoot database connectivity, transaction management, and query performance.

## Learning Outcomes

By exploring this project, developers can build foundational knowledge of:

- Java database programming.
- Hibernate ORM fundamentals.
- Entity-to-table mapping.
- Database CRUD operations.
- Session and transaction management.
- Primary key concepts.
- Hibernate configuration.
- JDBC and MySQL integration.
- Querying relational data through an ORM framework.

## Future Enhancements

The project can be extended with the following improvements:

- Add Maven or Gradle for dependency management.
- Upgrade to a compatible modern Hibernate version.
- Replace XML entity mappings with JPA annotations, if appropriate.
- Add Bean Validation for input validation.
- Implement a service and repository layer.
- Add pagination and sorting.
- Introduce connection pooling.
- Add unit and integration tests.
- Externalize database credentials through environment variables.
- Integrate Hibernate into a Spring Boot REST API.
- Add Docker Compose for a reproducible MySQL development environment.

These are potential enhancements rather than features claimed to exist in the current implementation.

## References and Resources

### Official Documentation

- [Hibernate ORM](https://hibernate.org/orm/)  
  Official Hibernate ORM project and documentation.

- [Hibernate Documentation](https://docs.jboss.org/hibernate/orm/current/userguide/html_single/Hibernate_User_Guide.html)  
  Reference for sessions, entity mappings, persistence, queries, and transactions.

- [Jakarta Persistence](https://jakarta.ee/specifications/persistence/)  
  Specification for Java object-relational persistence.

- [MySQL Documentation](https://dev.mysql.com/doc/)  
  Official MySQL installation, SQL, and database administration documentation.

- [MySQL Connector/J](https://dev.mysql.com/doc/connector-j/en/)  
  Documentation for the MySQL JDBC driver.

- [Java Documentation](https://docs.oracle.com/en/java/)  
  Official Java platform documentation.

- [Eclipse IDE](https://www.eclipse.org/ide/)  
  Java development environment.

### Source Code

- [Complete GitHub Repository](https://github.com/akshayKarai/Hibernate-operations)
- [Student Entity](https://github.com/akshayKarai/Hibernate-operations/blob/master/Student.java)
- [Hibernate Configuration](https://github.com/akshayKarai/Hibernate-operations/blob/master/hibernate.cfg.xml)
- [Create Example](https://github.com/akshayKarai/Hibernate-operations/blob/master/CreateStudentDemo.java)
- [Read Example](https://github.com/akshayKarai/Hibernate-operations/blob/master/ReadStudentDemo.java)
- [Query Example](https://github.com/akshayKarai/Hibernate-operations/blob/master/QueryStudentDemo.java)
- [Update Example](https://github.com/akshayKarai/Hibernate-operations/blob/master/UpdateStudentDemo.java)
- [Delete Example](https://github.com/akshayKarai/Hibernate-operations/blob/master/DeleteStudentDemo.java)
- [Primary Key Example](https://github.com/akshayKarai/Hibernate-operations/blob/master/PrimaryKeyDemo.java)
- [JDBC Example](https://github.com/akshayKarai/Hibernate-operations/blob/master/TestJdbc.java)

## Author

**Akshay Karai**

GitHub: [@akshayKarai](https://github.com/akshayKarai)

---

This repository is intended for educational purposes and demonstrates foundational database operations using Java, Hibernate, and MySQL.
