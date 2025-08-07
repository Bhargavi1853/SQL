# Task 3 – SQL SELECT Query Practice

This task demonstrates the use of SQL `SELECT` queries to retrieve data from a student attendance system database using filtering, sorting, and limiting techniques.


## Basic SQL Command Definitions

| Command      | Definition                                                                |
| ------------ | ------------------------------------------------------------------------- |
| `SELECT`     | Retrieves data from one or more tables.                                   |
| `FROM`       | Specifies the table to retrieve data from.                                |
| `WHERE`      | Filters records based on specified condition(s).                          |
| `AND` / `OR` | Combines multiple conditions in the `WHERE` clause.                       |
| `ORDER BY`   | Sorts the result set in ascending (`ASC`) or descending (`DESC`) order.   |
| `LIMIT`      | Limits the number of rows returned.                                       |
| `BETWEEN`    | Filters results within a specified range.                                 |
| `LIKE`       | Searches for a specified pattern in a column (not used here, but useful). |

---

### 1. Using SELECT (*) Commands To view all rows in a Table

View all records in the **attendance** table.

```sql
SELECT * FROM attendance;
```

- Retrieves all attendance data including student ID, class ID, and status.


View all records in the **class** table

```sql
SELECT * FROM class;
```

- Displays all classes along with course ID, date, and faculty name.

View all records in the **course** table

```sql
SELECT * FROM course;
```

- Lists all courses with their department associations.

View all records in the **student** table

```sql
SELECT * FROM student;
```

- Displays all students, their names, emails, and department IDs.

View all records in the **department** table

```sql
SELECT * FROM department;
```

- Shows all departments available in the system.

---

<img width="561" height="430" alt="output of select2" src="https://github.com/user-attachments/assets/3d6bbb50-6819-4946-994c-fa26bbf2fae3" />
<img width="574" height="906" alt="Output of select" src="https://github.com/user-attachments/assets/c575a640-72cc-417d-91e1-953afc98ddc1" />

---


### 2. Filtering with `WHERE` clause

```sql
    SELECT * FROM attendance WHERE std_id = 101;
```

```sql
    SELECT * FROM attendance WHERE status = 'absent';
```

```sql
    SELECT * FROM course WHERE dept_id = 2;
```
---

### 3. Combining filters using `AND`

```sql
SELECT * FROM attendance WHERE status = 'absent' AND std_id = 103;
```

- Shows only the records where student 103 was absent.

---

<img width="647" height="700" alt="WHERE Command" src="https://github.com/user-attachments/assets/f6b7660d-b01f-487b-b0e5-801ae7f62c88" />

---


### 4. Sorting data using `ORDER BY`

```sql
SELECT * FROM attendance ORDER BY class_id;
```

- Sorts attendance records by class ID in ascending order.

---

<img width="553" height="322" alt="ORDER BY" src="https://github.com/user-attachments/assets/f4adc1e8-5ae1-47b7-bb20-37fc418bb86d" />

---

### 5. Sorting data in descending order using `ORDER BY DESC`

```sql
SELECT * FROM attendance ORDER BY class_id DESC;
```

- Shows attendance sorted by class ID from latest to earliest.

---

### 6. Sorting by student ID using `ORDER BY ASC`

```sql
SELECT * FROM attendance ORDER BY std_id ASC;
```

- Displays all attendance sorted by student ID in ascending order.

---

<img width="592" height="637" alt="ORDER BY with ASC-DESC" src="https://github.com/user-attachments/assets/b58dfd2f-f312-4249-b2f8-f3c2bfc90f01" />

---

### 7. Using `LIMIT` with `ORDER BY`

```sql
SELECT * FROM attendance ORDER BY std_id ASC LIMIT 5;
```

- Fetches only the first 5 rows of attendance when sorted by student ID.

```sql
SELECT * FROM attendance ORDER BY class_id LIMIT 5;
```

- Fetches first 5 rows sorted by class ID.

---

<img width="579" height="409" alt="LIMIT" src="https://github.com/user-attachments/assets/398fed02-b5e7-4805-893a-71578a27448c" />


---

### 8. Filtering between ranges using `BETWEEN`

```sql
SELECT * FROM class WHERE date BETWEEN '2025-08-01' AND '2025-08-03';
```

- Returns all classes scheduled within the date range.

```sql
SELECT * FROM attendance WHERE atd_id BETWEEN 401 AND 405;
```

- Filters attendance records whose IDs are between 401 and 405.

---

<img width="766" height="447" alt="BETWEEN" src="https://github.com/user-attachments/assets/f564ab42-6a4c-4c50-9419-a7da629d259f" />


---

## Summary

- These queries form the backbone of data retrieval in SQL.

- By learning `SELECT`, `WHERE`, `ORDER BY`, `LIMIT`, 'LIKE', 'AND/OR' and `BETWEEN`, you can filter and analyze records efficiently in any relational database system.

- These SQL queries help retrieve, sort, and filter data in various ways, which is essential in real-world database-driven applications. 

This exercise improves the confidence in using MySQL for data analysis and reporting.
