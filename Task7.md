# Task 7 – SQL Views

This task demonstrates the creation and usage of **SQL Views** in the Student Attendance System database.
Views provide a way to simplify complex queries, improve security, and present customized data to users without exposing the underlying tables.

---

## Basic SQL Command Definitions

| Command             | Definition                                                                 |
| ------------------- | -------------------------------------------------------------------------- |
| `VIEW`              | A virtual table created from a query result, stored for reusability.       |
| `CREATE VIEW`       | Creates a view based on a `SELECT` query.                                  |
| `SELECT FROM VIEW`  | Retrieves data from a view just like from a normal table.                  |
| `DROP VIEW`         | Deletes a view definition from the database.                               |
| `WITH CHECK OPTION` | Ensures that all modifications through the view satisfy the view’s filter. |

---

### 1. Student Marks View

A view that shows each student’s marks along with course details.

* Simplifies repeated queries for marks data.
* Useful for quick reporting.


### 2. Student Attendance View

A view displaying attendance records for students across courses.

* Joins student, course, and attendance data.
* Useful for analyzing student participation.



### 3. Department Summary View

A view that summarizes data **per department**, including:

* Total students in each department.
* Average marks of students in that department.


### 4. High Performers View

A view listing students whose **average marks** are above a threshold (e.g., 40).

* Helps identify top-performing students.
* Demonstrates use of `HAVING` with `GROUP BY`.


### 5. Attendance Percentage View

A view calculating **attendance percentage** per student.

* Uses conditional aggregation with `CASE`.
* Helps track student discipline and consistency.


### 6. Restricted View with `WITH CHECK OPTION`

A view that only allows access to **Computer Science students**.

* Ensures inserts/updates through the view must meet the filter condition.
* Adds a layer of **data security**.


### 7. Dropping Views

Views that are no longer needed can be removed using `DROP VIEW`.

* Helps keep the database clean.
* Prevents clutter from outdated definitions.

---

## Summary

* Views simplify **complex queries** and improve query reusability.
* They can be used for:

  * Simplifying joins.
  * Aggregating results.
  * Restricting access (security).
  * Reporting and analytics.
* This task demonstrated different types of views including **simple views, join-based views, aggregated views, conditional views, percentage views, and restricted views**.

By mastering views, one can create a **cleaner abstraction layer** over raw tables and provide user-friendly data access.

---

## Outcomes

- Gained hands-on experience in creating and managing SQL Views.

- Learned how views can simplify complex queries by reusing stored logic.

- Understood how to join multiple tables inside a view for student marks and attendance reporting.

- Built analytical views such as average marks, attendance percentages, and department summaries.

- Practiced using WITH CHECK OPTION to enforce security and ensure valid data updates.

- Learned how to manage database cleanup by dropping unnecessary views.

- Improved understanding of how views can be applied in real-world reporting and data security scenarios.



<img width="901" height="419" alt="Screenshot 2025-08-16 181456" src="https://github.com/user-attachments/assets/4b6cc1f5-152c-4b7c-b0e3-85d67e2cd5f1" />
<img width="980" height="506" alt="Screenshot 2025-08-16 181257" src="https://github.com/user-attachments/assets/dff4b7b5-f1b3-49a2-ae38-eec8ef91142d" />
<img width="998" height="499" alt="Screenshot 2025-08-16 181227" src="https://github.com/user-attachments/assets/640d8eb7-05d2-4aed-96aa-a3e3bb095054" />
<img width="999" height="446" alt="Screenshot 2025-08-16 181204" src="https://github.com/user-attachments/assets/651e82a1-3e36-4238-a215-f33a7b0a90ad" />
<img width="984" height="837" alt="Screenshot 2025-08-16 181130" src="https://github.com/user-attachments/assets/771813e2-026a-408f-bd4f-2f578b630465" />
<img width="944" height="726" alt="Screenshot 2025-08-16 181045" src="https://github.com/user-attachments/assets/79c9c5f0-543d-4693-a6f7-c1947d265dae" />

