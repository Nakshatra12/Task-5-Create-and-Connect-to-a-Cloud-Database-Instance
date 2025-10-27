# Task-5-Create-and-Connect-to-a-Cloud-Database-Instance

To understand how Cloud Databases work by creating a managed SQL database instance (like MySQL or PostgreSQL) in the cloud, connecting to it, and performing basic operations.

### I created a MySQL database instance using Google Cloud SQL to explore Database-as-a-Service. After setting up public access, I connected using MySQL Workbench and executed SQL queries to create and manage data in a table. This task helped me understand how cloud databases are deployed, secured, and accessed remotely, which is essential for building scalable and reliable cloud applications.


## Concept Overview

### Concept	Description

Cloud SQL:        A fully managed relational database service provided by Google Cloud for MySQL, PostgreSQL, and SQL Server.

DBaaS:          	Database-as-a-Service — where the cloud provider manages maintenance, scaling, and security of databases.

CRUD Operations:	Create, Read, Update, and Delete — the four basic operations in a database.


## Tools Used

Google Cloud Console:  	To create and manage the Cloud SQL instance.

MySQL:  The database engine used for this task.

Cloud Shell:  To connect and run SQL commands.


## Step-by-Step Implementation

### 1️⃣ Step 1 – Create a MySQL Instance in Cloud SQL

Go to Google Cloud Console → Cloud SQL

#### Click “Create Instance”

Select MySQL

#### Configure the instance:

  Instance ID: intern-sql-instance

  Password: (Create a secure password)

  Region: Choose the nearest (e.g., asia-south1)

  Database Version: MySQL 8.x

  Machine Type: Shared core (Smallest tier)

  Storage: 10 GB (default)

#### Click “Create Instance”

### ⏳ Wait for a few minutes until the instance status changes to RUNNING.

### 2️⃣ Step 2 – Configure Public Access

1. Open your created instance in Cloud SQL.

2.Go to Connections → Networking → Public IP section.

3.Click Add Network → enter:

  Name: Local Access

  Network: your public IP (Find it by searching “What is my IP” on Google, e.g., 103.xx.xx.xx/32)

4.Save changes.

### 3️⃣ Step 3 – Get Connection Details

In the Overview tab, note the following:

1.Public IP Address

2.Instance connection name

3.Database version

You’ll need these for connecting from your local tool or terminal.

### 4️⃣ Step 4 – Connect to the Instance
#### Using Cloud Shell

1.Open Cloud Shell from the GCP console.

2.Run the command:
gcloud sql connect intern-sql-instance --user=root

3.Enter your password when prompted.

You are now connected to the MySQL shell of your instance.

### 5️⃣ Step 5 – Create Database and Table

#### Run these commands in Cloud Shell:

CREATE DATABASE intern_demo;

USE intern_demo;

CREATE TABLE students (
  
  id INT AUTO_INCREMENT PRIMARY KEY,
  
  name VARCHAR(50),
  
  domain VARCHAR(30),
  
  score INT

);

### 6️⃣ Step 6 – Insert and Retrieve Data

INSERT INTO students (name, domain, score)

VALUES 

('Aarav', 'Cloud', 95),

('Diya', 'DevOps', 89),

('Rohan', 'AI', 92);


SELECT * FROM students;

### 7️⃣ Step 7 – Update data
UPDATE students
SET score = 98
WHERE name = 'Aarav';

### 8️⃣ Step 8 - Delete data
DELETE FROM students
WHERE name = 'Diya';

## Deliverables

### Deliverable	Description

✅ Screenshot 1	Cloud SQL Selection

✅ Screenshot 2	Click on Create Instance & fill the details

✅ Screenshot 3	Choose MySQL Database

✅ Screenshot 4	Instance Created Successfully

✅ Screenshot 5	Authorized Network Added Successfully

✅ Screenshot 6 Connect via Cloud Shell

✅ Screenshot 7 Create Database & Table

✅ Screenshot 8 Insert & Retrieve Data

✅ Screenshot 9 Update Data

✅ Screenshot 10 Delete 

✅ Screenshot 11 Stop Instance to prevent ongoing usage & billing

✅ Screenshot 12 Delete Instance

✅ SQL File	   All SQL commands used


## Key Learning Outcomes

1.Understanding of Cloud SQL and DBaaS

2.Steps to create and configure a cloud database instance

3.Practical knowledge of remote SQL connections

4.Hands-on with CRUD operations

5.Awareness of cloud networking and access control

