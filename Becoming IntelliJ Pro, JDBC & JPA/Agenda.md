# Java Persistence & OO Design "Under the Hood"

## 📅 Day 1: The Developer’s Workbench & SQL Foundation
*Goal: Master the IDE and align on the relational data layer.*

### IntelliJ Power Moves
* **Navigation & Editing:** Search Everywhere (`Shift+Shift`), Go to Implementation (`Ctrl+Alt+B`), and Multi-cursor editing.
* **Troubleshooting:** * Advanced Debugger: Conditional breakpoints and "Force Step Into".
  * Evaluating expressions and changing variable values at runtime to test "what-if" scenarios.

### SQL Revision & Schema Design
* **Relational Concepts:** Normalization, Indexes, and Execution Plans.
* **ACID Properties:** A deep dive into Atomicity, Consistency, Isolation, and Durability.
* **Hands-on Lab:** Designing a relational schema for a "Task Tracking" or "Inventory" system.

### JDBC Architecture

---

## 📅 Day 2: JDBC – Demystifying Connectivity & Raw Transactions
*Goal: Understand low-level communication and manual transaction control.*

### Topics
* **JDBC Driver Internals:** How the `DriverManager` loads vendor-specific JARs.
* **The Lifecycle:** Manual management of `Connection`, `Statement`, and `ResultSet`.
* **Low-Level Transactions:** * Disabling `autoCommit`.
  * Manual `connection.commit()` and `connection.rollback()`.
  * Understanding **Transaction Isolation Levels** (Read Committed vs. Serializable).
* **Connection Pooling:** Implementing **HikariCP** and understanding pool-level transaction behavior.
* JPA Introduction 
  * Purpose - Why? What? How?


### Hands-on Lab
* Building a JDBC utility that executes multiple SQL statements and rolls them back if a single one fails.

---

## 📅 Day 3: JPA – Manual ORM & Object State
*Goal: Transition to JPA while managing the "Magic" manually.*

### Topics
* **JPA Specification:** Setting up `META-INF/persistence.xml` and the `EntityManagerFactory`.
* **JPA Transactions:** * Using the `EntityTransaction` API.
  * Difference between `flush()` and `commit()`.
* **Entity Lifecycle:** Lifecyle Methods Involved
* **Mapping Foundations:** `@Entity`, `@Id`, and relationship mapping (`@ManyToOne`, `@OneToMany`).

### Hands-on Lab
* Refactoring Day 2 logic to use JPA, focusing on manual `tx.begin()` and `tx.commit()` blocks.

---

## 📅 Day 5: Synthesis – OO Design & The Service Layer
*Goal: Build an application using pure OO principles and manual dependency wiring.*

### Topics: The "Unit of Work" Challenge
* **The Service Layer:** Why we need it to manage business Logic that span multiple Repositories/DAOs.
* **Manual Transaction Propagation:** How to share a single `EntityManager` across different classes to ensure they participate in the same transaction (Manual Dependency Injection).
* **OO Design Focus:** * **Dependency Inversion:** Passing the `EntityManager` through constructors.
  * **Exception Handling:** Translating SQL/JPA exceptions into meaningful business exceptions.

### Final Project: Framework-less CRUD Application
* Build a standalone CLI application with a Service layer that handles:
  1. Opening a Transaction.
  2. Calling multiple DAO's.
  3. Committing or Rolling back based on business logic success/failure.



---

## 🛠 Tech Stack
* **Language:** Java 17+
* **Database:** MySQL or PostgreSQL
* **ORM:** Hibernate (JPA Implementation)
* **Testing:** JUnit (Orchestration)
* **Pooling:** HikariCP
* **Build Tool:** Maven