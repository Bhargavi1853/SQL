# Task 5 – SQL Joins (Inner, Left, Right, Full)

This task demonstrates the use of SQL JOIN operations to combine and analyze data across multiple tables in the Student Attendance System. Joins allow us to fetch related information stored in different tables and present it as a single, unified view.

## Basic SQL Join Definitions
### Join Type	Definition
- `INNER JOIN`	Returns rows that have matching values in both tables.

- `LEFT JOIN`	Returns all rows from the left table, and matching rows from the right.

- `RIGHT JOIN`	Returns all rows from the right table, and matching rows from the left.

- `FULL OUTER` JOIN	Combines the results of both left and right joins, showing all records.

---

### Joins in Student Attendance System
1. INNER JOIN

- Combines records only when there is a match between tables.

- Example usages in this task:

    - Students with their respective departments.

    - Courses with the departments they belong to.

    - Classes with their course names.

    - Attendance details linked to students and courses.

    - Marks with student names and course names.


2. LEFT JOIN

- Returns all rows from the left table even if there is no match in the right table.

- Example usages in this task:

    - Display all students even if they don’t have attendance records.

    - Show all students even if they don’t have marks yet.

    - List all courses even if no department is assigned.


3. RIGHT JOIN

- Returns all rows from the right table even if there is no match in the left table.

- Example usages in this task:

    - Ensure all departments are shown even if some have no students.

    - Ensure all courses are shown even if they don’t belong to any department.

    - Ensure all students appear even if their marks are missing.


4. FULL OUTER JOIN

- Combines results from both left and right joins.

- Since MySQL doesn’t directly support FULL JOIN, it is achieved using UNION of LEFT and RIGHT joins.

- Example usages in this task:

    - Combine students and marks so that all students and all marks are displayed, even when some don’t match.

    - Combine courses and classes to show all entries, even those without connections.

---

### Outcome

- By performing these joins across all six tables — student, department, course, class, attendance, and marks — this task:

    - Strengthens understanding of relationships in relational databases.

<img width="550" height="936" alt="image" src="https://github.com/user-attachments/assets/f9a38b31-71ec-4322-94a3-42e71504e625" />
<img width="492" height="870" alt="Screenshot 2025-08-16 172916" src="https://github.com/user-attachments/assets/2988a661-a5b4-4f5b-a842-f473b7765cc5" />
<img width="505" height="567" alt="Screenshot 2025-08-16 173051" src="https://github.com/user-attachments/assets/cdd6292f-e79c-4ff6-b3f3-5c6b7a0b949c" />
<img width="510" height="577" alt="Screenshot 2025-08-16 173031" src="https://github.com/user-attachments/assets/3fd5cc98-7f15-4c0f-b915-95157b5371fd" />
<img width="511" height="545" alt="Screenshot 2025-08-16 173016" src="https://github.com/user-attachments/assets/778a087e-75d4-4893-9aae-8c8648931883" />


- Demonstrates how to fetch meaningful combined results across different entities.

- Shows the practical use of INNER, LEFT, RIGHT, and FULL joins in handling real-world queries.
