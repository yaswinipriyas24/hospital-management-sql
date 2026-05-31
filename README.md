# 🏥 Hospital Management SQL Database

## 📌 Elevate Labs Internship – Task 1

This project was completed as part of the **Elevate Labs SQL Developer Internship – Task 1: Database Setup and Schema Design**.

### 🎯 Objective
The objective of this task is to learn how to:

- Create databases and tables
- Define relationships between tables
- Use Primary Keys and Foreign Keys
- Understand schema design and ER diagrams

Task requirements included database creation, schema design, relationships, SQL script generation, and ER diagram creation. :contentReference[oaicite:2]{index=2}

---

# 🏥 Project Overview

This project represents a **Hospital Management Database System** designed using **PostgreSQL (pgAdmin 4)**.

The database stores and manages information related to:

- Patients
- Doctors
- Departments
- Appointments

The system demonstrates how relational databases work by connecting multiple tables using **Primary Keys** and **Foreign Keys**.

---

# 🛠 Tools Used

- PostgreSQL
- pgAdmin 4
- SQL (DDL)
- GitHub

---

# 🗂 Database Schema Design

The following tables were created:

### 1. Patients Table
Stores patient information.

Columns:
- patient_id (Primary Key)
- patient_name
- age
- gender
- phone_number

### 2. Doctors Table
Stores doctor information.

Columns:
- doctor_id (Primary Key)
- doctor_name
- specialization
- phone_number

### 3. Departments Table
Stores hospital department details.

Columns:
- department_id (Primary Key)
- department_name

### 4. Appointments Table
Stores appointment information and connects all entities.

Columns:
- appointment_id (Primary Key)
- patient_id (Foreign Key)
- doctor_id (Foreign Key)
- department_id (Foreign Key)
- appointment_date

---

# 🔗 Relationships Used

The following relationships were implemented:

- One Patient → Many Appointments
- One Doctor → Many Appointments
- One Department → Many Appointments

Foreign keys were used to maintain proper relationships between tables.

---

# ⚙️ Step-by-Step Process Followed

### Step 1: Created Database
Created a database named:

```sql
hospital_management
```

### Step 2: Created Tables
Created:

- Patients
- Doctors
- Departments
- Appointments

using `CREATE TABLE`.

### Step 3: Added Primary Keys
Used:

```sql
PRIMARY KEY
```

to uniquely identify each record.

### Step 4: Added Foreign Keys
Used:

```sql
FOREIGN KEY
```

to connect tables.

Example:

```sql
FOREIGN KEY (patient_id)
REFERENCES Patients(patient_id)
```

### Step 5: Inserted Sample Data
Inserted sample records into:

- Patients
- Doctors
- Departments
- Appointments

to test database relationships.

### Step 6: Generated ER Diagram
Created an ER diagram in pgAdmin 4 to visualize relationships between tables.

### Step 7: Exported SQL Script
Generated SQL schema script using PostgreSQL backup in `.sql` format.

---

# 🧠 Key Concepts Learned

- DDL (Data Definition Language)
- Normalization
- Primary Key
- Foreign Key
- ER Diagram
- Relationships in DBMS

---

# 🖼 ER Diagram

Add your ER diagram screenshot here.

Example:

```md
![ER Diagram](er_diagram.png)
```

---

# ❓ Interview Questions and Answers

### 1. What is normalization?

Normalization is the process of organizing data in a database to reduce redundancy and improve data consistency.

### 2. Explain Primary Key vs Foreign Key.

**Primary Key:**  
Uniquely identifies each record in a table.

**Foreign Key:**  
Creates relationships between tables by referencing a primary key from another table.

### 3. What are constraints?

Constraints are rules applied to columns to maintain data accuracy and integrity.

Examples:
- PRIMARY KEY
- FOREIGN KEY
- NOT NULL
- UNIQUE

### 4. What is a surrogate key?

A surrogate key is an automatically generated unique identifier such as `SERIAL` or `AUTO_INCREMENT`.

### 5. How do you avoid data redundancy?

Data redundancy can be avoided using normalization and proper table relationships.

### 6. What is an ER diagram?

An Entity Relationship (ER) Diagram visually represents tables and relationships in a database.

### 7. What are the types of relationships in DBMS?

- One-to-One
- One-to-Many
- Many-to-Many

### 8. Explain the purpose of AUTO_INCREMENT.

AUTO_INCREMENT automatically generates unique IDs for new records.

(In PostgreSQL, `SERIAL` is commonly used instead.)

### 9. What is the default storage engine in MySQL?

The default storage engine in MySQL is **InnoDB**.

### 10. What is a composite key?

A composite key is a key formed using two or more columns together.

---

# 🚧 Challenges Faced and Solutions

### 1. Character Length Error

**Problem:**

```text
value too long for type character varying
```

**Reason:**
The inserted value exceeded the defined column size.

**Solution:**
Updated the column size using:

```sql
ALTER TABLE Doctors
ALTER COLUMN specialization TYPE VARCHAR(100);
```

---

### 2. Foreign Key Constraint Error

**Problem:**

```text
violates foreign key constraint
```

**Reason:**
Referenced ID was not present in the parent table.

**Solution:**
Inserted data into parent tables before inserting appointment records.

---

### 3. SQL Export Issue

**Problem:**
Generated encoded-looking SQL dump.

**Solution:**
Used PostgreSQL backup with:

- Format = Plain
- Only Schemas = ON

to generate a readable `.sql` script.

---

# 📂 Project Structure

```text
hospital-management-sql/
│── hospital_management.sql
│── er_diagram.png
│── README.md
```

---

# ✅ Outcome

Successfully designed a well-structured hospital management database schema with proper relationships, SQL scripts, and ER diagram as part of Elevate Labs Internship Task 1.

---

## 👩‍💻 Author

**Yaswinipriya Sesetti**

LinkedIn:  
https://www.linkedin.com/in/sesetti-yaswini-priya-95811925a
