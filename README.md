# Task 4 – SQL Aggregate Functions, GROUP BY, and HAVING

This task demonstrates the use of SQL **Aggregate functions** such as `COUNT`, `SUM`, `AVG`, `MAX`, and `MIN` in combination with `GROUP BY` and `HAVING` to summarize and filter grouped data from a **Student Attendance System** database.

---

## Basic SQL Command Definitions

| Command    | Definition                                                       |
| ---------- | ---------------------------------------------------------------- |
| `SELECT`   | Retrieves data from one or more tables.                          |
| `FROM`     | Specifies the table(s) to retrieve data from.                    |
| `JOIN`     | Combines rows from two or more tables based on related columns.  |
| `GROUP BY` | Groups rows with the same values into summary rows.              |
| `HAVING`   | Filters the results of grouped records (used after aggregation). |
| `COUNT()`  | Returns the number of rows.                                      |
| `SUM()`    | Returns the total sum of a numeric column.                       |
| `AVG()`    | Returns the average value of a numeric column.                   |
| `MAX()`    | Returns the highest value in a set.                              |
| `MIN()`    | Returns the lowest value in a set.                               |


---
### Created a new marks Table and added rows 

-- create marks table (MySQL)

```sql
CREATE TABLE marks (
    mark_id INT PRIMARY KEY AUTO_INCREMENT,
    std_id INT,
    course_id INT,
    marks_obtained FLOAT,
    FOREIGN KEY (std_id) REFERENCES student(std_id),
    FOREIGN KEY (course_id) REFERENCES course(course_id)
);
```

-- inserted rows in marks table

```sql
INSERT INTO marks (std_id, course_id, marks_obtained) VALUES
(101, 201, 42),
(101, 203, 35),
(102, 202, 44),
(102, 204, 40),
(102, 210, 38),
(103, 205, 46),
(103, 207, 41),
(104, 203, 36),
(104, 209, 39),
(105, 206, 45),
(105, 208, 43);
```
- Here, didn't added mark_id because of AUTO INCREMENT command, the mark_id will be generated automatically.
  
-- verify

```sql
SELECT * FROM marks;
```
<img width="455" height="758" alt="Viewing all the rows in marks and attendance tables" src="https://github.com/user-attachments/assets/28ceb572-774c-4abb-b5e6-a37ad8a1bda6" />

---

### 0. View All Marks with Course and Student Details

```sql
SELECT 
    m.std_id,
    s.std_name,
    m.course_id,
    c.course_name,
    m.marks_obtained
FROM marks m
JOIN student s ON m.std_id = s.std_id
JOIN course c ON m.course_id = c.course_id
ORDER BY m.std_id, m.course_id;
```

* Joins the **marks**, **student**, and **course** tables.
* Displays each student’s marks along with their **name** and the **course name**.
* Orders the results by **student ID** and then **course ID** for better readability.


<img width="633" height="405" alt="View all marks with course and student tables" src="https://github.com/user-attachments/assets/7efd6307-2c0c-4ee7-be69-eecf56fa56be" />

---

### 1. Count total students in each department

```sql
SELECT d.dept_name, COUNT(s.std_id) AS total_students
FROM department d
JOIN student s ON d.dept_id = s.dept_id
GROUP BY d.dept_name;
```

- Shows how many students belong to each department.

---

### 2. Count total classes conducted for each course

```sql
SELECT c.course_name, COUNT(cl.class_id) AS total_classes
FROM course c
JOIN class cl ON c.course_id = cl.course_id
GROUP BY c.course_name;
```

- Displays the number of class sessions held for each course.

---

### 3. Count attendance status per course

```sql
SELECT c.course_name, a.status, COUNT(a.atd_id) AS total
FROM attendance a
JOIN class cl ON a.class_id = cl.class_id
JOIN course c ON cl.course_id = c.course_id
GROUP BY c.course_name, a.status;
```

- Breaks down the number of “present” and “absent” statuses for each course.
<img width="618" height="904" alt="COUNT2" src="https://github.com/user-attachments/assets/a5ed26a5-d16d-4abd-9661-5bd931cf829f" />

---

### 4. Average marks obtained in each course

```sql
SELECT c.course_name, AVG(m.marks_obtained) AS avg_marks
FROM marks m
JOIN course c ON m.course_id = c.course_id
GROUP BY c.course_name;
```

- Calculates the average score for each course.
<img width="679" height="368" alt="AVG" src="https://github.com/user-attachments/assets/14117e5b-c89f-488c-9825-8bb588f01b58" />

---

### 5. Total sum marks per student

```sql
SELECT s.std_name, SUM(m.marks_obtained) AS total_marks
FROM student s
JOIN marks m ON s.std_id = m.std_id
GROUP BY s.std_name;
```

- Displays the total marks scored by each student.
<img width="668" height="279" alt="sum" src="https://github.com/user-attachments/assets/37cc5f70-10bf-46ea-8fd8-7cb5f4046060" />

---

### 6. Students with average marks above 40 (HAVING)

```sql
SELECT s.std_name, AVG(m.marks_obtained) AS avg_marks
FROM student s
JOIN marks m ON s.std_id = m.std_id
GROUP BY s.std_name
HAVING AVG(m.marks_obtained) > 40;
```

- Shows only those students whose average marks are greater than 40.

---

### 7. Students who attended more than 2 classes (HAVING)

```sql
SELECT s.std_name, COUNT(a.atd_id) AS total_present
FROM student s
JOIN attendance a ON s.std_id = a.std_id
WHERE a.status = 'present'
GROUP BY s.std_name
HAVING COUNT(a.atd_id) > 2;
```

- Displays students with more than two present records.

img width="568" height="453" alt="AVG with HAVING" src="https://github.com/user-attachments/assets/e8d2ee7a-6cef-482d-b8bf-0dba2f494dd9" />

---

### 8. Count total presents per student

```sql
SELECT s.std_name, COUNT(a.atd_id) AS presents
FROM student s
JOIN attendance a ON s.std_id = a.std_id
WHERE a.status = 'present'
GROUP BY s.std_name;
```

- Shows the total number of “present” entries for each student.

---

### 9. Count total absents per student

```sql
SELECT s.std_name, COUNT(a.atd_id) AS absents
FROM student s
JOIN attendance a ON s.std_id = a.std_id
WHERE a.status = 'absent'
GROUP BY s.std_name;
```

- Shows the total number of “absent” entries for each student.
  
<img width="682" height="731" alt="COUNT3" src="https://github.com/user-attachments/assets/34abbf36-b0d9-413d-a148-95e45ceeb545" />

---

### 10. Highest marks obtained in each course

```sql
SELECT c.course_name, MAX(m.marks_obtained) AS highest_marks
FROM marks m
JOIN course c ON m.course_id = c.course_id
GROUP BY c.course_name;
```

- Finds the highest mark scored in each course.

---

### 11. Lowest marks obtained in each course

```sql
SELECT c.course_name, MIN(m.marks_obtained) AS lowest_marks
FROM marks m
JOIN course c ON m.course_id = c.course_id
GROUP BY c.course_name;
```

- Finds the lowest mark scored in each course.
  
<img width="840" height="917" alt="MAX,MIN" src="https://github.com/user-attachments/assets/ff890585-1119-4cd2-82fb-745e1444d026" />

---

## Summary

* `GROUP BY` helps summarize data by grouping rows based on common values.
* Aggregate functions (`COUNT`, `SUM`, `AVG`, `MAX`, `MIN`) provide quick statistics for each group.
* `HAVING` allows filtering of groups after aggregation.
* These queries are crucial for reporting and analytics in database-driven applications.
