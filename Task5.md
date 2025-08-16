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

- Demonstrates how to fetch meaningful combined results across different entities.

- Shows the practical use of INNER, LEFT, RIGHT, and FULL joins in handling real-world queries.
