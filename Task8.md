# Task 8 – SQL Stored Procedures and Functions

This task demonstrates the use of **Stored Procedures** and **User-Defined Functions (UDFs)** in SQL. These allow us to encapsulate logic inside the database for reusability, modularity, and better performance.

---

## Basic SQL Command Definitions

| Command / Concept  | Definition                                                                 |
| ------------------ | -------------------------------------------------------------------------- |
| `CREATE PROCEDURE` | Defines a stored procedure that can be called later with `CALL`.           |
| `CALL`             | Executes a stored procedure.                                               |
| `CREATE FUNCTION`  | Defines a function that returns a single value.                            |
| `RETURNS`          | Specifies the return data type for a function.                             |
| `DELIMITER`        | Changes the command separator to allow multi-line procedure/function code. |
| `IN` parameter     | Input parameter passed into a procedure/function.                          |

---

## Stored Procedures

### 1. `GetAttendanceByStudent`

Retrieves all attendance records for a specific student.

```sql
CALL GetAttendanceByStudent(101);
```

---

### 2. `GetMarksByStudent`

Displays all marks obtained by a student across different courses.

```sql
CALL GetMarksByStudent(102);
```

---

### 3. `GetCourseAttendanceSummary`

Provides a course-wise summary of **present** and **absent** counts.

```sql
CALL GetCourseAttendanceSummary();
```

---

### 4. `GetStudentPerformance`

Shows total and average marks for each student.

```sql
CALL GetStudentPerformance();
```

---

## Functions

### 1. `GetTotalMarks(student_id)`

Returns the total marks obtained by a student.

```sql
SELECT GetTotalMarks(101);
```

---

### 2. `GetAverageMarks(student_id)`

Returns the average marks of a student across all enrolled courses.

```sql
SELECT GetAverageMarks(103);
```

---

### 3. `GetAttendancePercentage(student_id)`

Calculates the percentage of classes attended by a student.

```sql
SELECT GetAttendancePercentage(105);
```

---

## Outcomes

- Learned how to create and use **stored procedures** to encapsulate queries.
- Practiced creating **functions** for reusable calculations like total marks, average, and attendance percentage.
- Gained experience with **parameters**, `CALL`, and `SELECT` for executing procedures and functions.
- Built a modular database system where repetitive logic can be centralized inside the DB.

<img width="872" height="394" alt="Screenshot 2025-08-16 184033" src="https://github.com/user-attachments/assets/de13e97b-d09a-47b7-8969-f64db07203fc" />
<img width="865" height="364" alt="Screenshot 2025-08-16 184012" src="https://github.com/user-attachments/assets/1e0e3842-6c96-46da-8ff4-6afff0960469" />
<img width="843" height="340" alt="Screenshot 2025-08-16 183812" src="https://github.com/user-attachments/assets/008020a6-98ff-4b32-8358-56247094a918" />

