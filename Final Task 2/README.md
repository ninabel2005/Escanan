# Finals Lab Task 2 - Transforming ER Model to Relational Tables #

This project is about converting an ER diagram of student assignment submissions into a MySQL database.
I created the tables, added sample data, and set the correct relationships using foreign keys.

## Sample Data Used ##
For this project, I used myself as the sample student.


## Step 1. Database Creation ##
I started by creating a new database called student_db and selected it for use.

CREATE DATABASE student_db; USE student_db; 

## Step 2. Tables Creation ## 
I made three tables: student, assignment, and submission.
student table has the student's username.
assignment table stores assignment details.
submission table links students and assignments, with a version number for each submission.
```sql
CREATE TABLE student ( username VARCHAR(50) PRIMARY KEY ); 
CREATE TABLE assignment ( shortname VARCHAR(50) PRIMARY KEY,
due_date DATE NOT NULL, url VARCHAR(255) DEFAULT NULL ); 
CREATE TABLE submission ( username VARCHAR(50), 
shortname VARCHAR(50), version INT, submit_date DATE NOT NULL, 
data TEXT, PRIMARY KEY (username, shortname, version), 
FOREIGN KEY (username) REFERENCES student(username) ON DELETE CASCADE ON UPDATE CASCADE,
FOREIGN KEY (shortname) REFERENCES assignment(shortname) ON DELETE CASCADE ON UPDATE CASCADE
); 
```
## Steps 3.  Inserting Sample Data ## 

I inserted sample records.

```sql
INSERT INTO student (username) VALUES ('Nina Escanan');
INSERT INTO assignment (shortname, due_date, url) VALUES ('MATH105', '2025-04-28', 'http://assignments.com/math105'), ('ENG102', '2025-05-10', 'http://assignments.com/eng102');
INSERT INTO submission (username, shortname, version, submit_date, data) VALUES ('Nina Escanan', 'MATH105', 1, '2025-04-27', 'First submission for Math'), 
('Nina Escanan', 'MATH105', 2, '2025-04-28', 'Updated Math submission'), ('Nina Escanan', 'ENG102', 1, '2025-05-09', 'English essay submission'); 
```
## Step 4. Showing the Tables ## 

Finally, I checked if the tables were created correctly.
```sql
SHOW TABLES;
```



## Here's the ERD ## 

 <img src="https://github.com/ninabel2005/Escanan/blob/main/Final%20Task%202/files2/image%20(1).png" alt="Alt Text" width="800" height="400"> 
