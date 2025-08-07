# Creation of Database and Table for Student Attendance System
The database student_attendance_system was created and used to define five core relational tables: department, student, course, class, and attendance.

## 1. Creating the Database

```sql
CREATE DATABASE student_attendance_system;
```
- This Query will create a Database named student_attendance_system.

```sql
USE student_attendance_system;
```

This command switches to the working database.

## 2. Creating Tables

#### Department Table
```sql
CREATE TABLE department (dept_id INT PRIMARY KEY,dept_name VARCHAR(100) NOT NULL);
```  
- dept_id: Primary Key
  
- dept_name: Department name (non-null)

#### Student Table

```sql
CREATE TABLE student (std_id INT PRIMARY KEY,std_name VARCHAR(100) NOT NULL,std_email VARCHAR(100) UNIQUE NOT NULL,dept_id INT,FOREIGN KEY (dept_id) REFERENCES department(dept_id));
```
  
  - References department table,
  
  - Email is unique,
  
 -  Foreign key on dept_id.
  
  
#### Course Table
  ```sql
CREATE TABLE course (course_id INT PRIMARY KEY,course_name VARCHAR(100) NOT NULL,dept_id INT,FOREIGN KEY (dept_id) REFERENCES department(dept_id));
  ```

  - Each course is linked to a department
  
  
  
  
#### Class Table
```sql  
CREATE TABLE class (class_id INT PRIMARY KEY,course_id INT,date DATE,faculty_name VARCHAR(100),FOREIGN KEY (course_id) REFERENCES course(course_id));
```

- Class refers to a course and includes date and faculty name
  
  
  
#### Attendance Table
```sql  
CREATE TABLE attendance (atd_id INT PRIMARY KEY,std_id INT,class_id INT,status ENUM('present', 'absent') NOT NULL,FOREIGN KEY (std_id) REFERENCES student(std_id),FOREIGN KEY (class_id) REFERENCES class(class_id));
```

- Tracks attendance status per student per class

- Foreign keys connect it to student and class

### Schema (Query: SHOW TABLES)

- Shows all five tables created:

   - attendance

   - class

   - course

   - department

   - student

<img width="1919" height="932" alt="Queries of Creating Databases and Tables" src="https://github.com/user-attachments/assets/494f4691-02c3-44ee-8e64-1eb84c86277b" />




### Output
The database student_attendance_system was successfully created.

- Five tables were created:
department, student, course, class, and attendance.

- All foreign key constraints were properly set up.

- SHOW TABLES; confirmed the existence of all five tables.

- DESCRIBE commands verified:

   - Primary keys are correctly defined.

   - Foreign keys are set with proper references.

   - Data types, null constraints, and unique fields are correctly structured.
<img width="720" height="923" alt="Queries Output" src="https://github.com/user-attachments/assets/21bedf02-84cc-40aa-9b2d-44c7c4b3c8e7" />



### ER Diagram

The ER (Entity-Relationship) diagram visually represents the logical structure of the Student Attendance System. It highlights the key entities and their relationships:


<img width="1536" height="1024" alt="ER_diagram" src="https://github.com/user-attachments/assets/30ff43ff-2e4a-4cce-bf7a-551d3a6bc406" />


Department

- Each department can have multiple students and multiple courses.

Student

- Belongs to one department.

- Can attend multiple classes.

- Linked to the attendance table via std_id.

Course

- Offered by one department.

- Can have multiple classes.

Class

- Represents a session for a particular course on a specific date.

- Handled by a faculty member.

- Connected to students through the attendance table.

Attendance

- Acts as a junction table between student and class.

- Stores each student’s attendance status (present or absent) for a specific class.

🔗 Relationships:

- One-to-many between department and student

- One-to-many between department and course

- One-to-many between course and class

- Many-to-many between student and class (via attendance)

- This design ensures normalized data storage, avoids redundancy, and supports efficient queries related to attendance tracking.


### Summary

+ This schema ensures data normalization and clear entity relationships.

+ All foreign keys enforce integrity and enable meaningful joins.

+ The use of ENUM in attendance ensures controlled input values.

