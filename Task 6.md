# Task 6 – SQL Subqueries and Nested Queries

This task demonstrates the use of **SQL subqueries and nested queries** to retrieve advanced insights from the Student Attendance System database. Subqueries allow us to use the result of one query inside another, enabling more complex data analysis.

---

## Basic SQL Command Definitions

| Command      | Definition                                                                    |
| ------------ | ----------------------------------------------------------------------------- |
| `SUBQUERY`   | A query nested inside another query to return a result set or a single value. |
| `IN`         | Used in a subquery to match multiple values from another query.               |
| `EXISTS`     | Returns true if the subquery returns one or more rows.                        |
| `CORRELATED` | A subquery that refers to a column from the outer query.                      |
| `FROM (..)`  | Derived table subquery, used as a temporary table in the main query.          |
| `SCALAR`     | Subquery returning a single value (like `MAX`, `AVG`, etc.).                  |

---

#### 1. Scalar Subquery – Compare with Average

Retrieve students who scored above the **overall average marks**.

* Demonstrates how to use a **single-value subquery**.
* Helps identify top performers.


#### 2. Subquery with `IN`

Find students who are enrolled in courses belonging to the **Computer Science department**.

* Demonstrates filtering using a list of values returned by a subquery.
* Useful when checking membership in related entities.


#### 3. Subquery with `EXISTS`

List students who have at least **one absent record** in attendance.

* Demonstrates using `EXISTS` to check for the presence of related records.
* Useful for existence checks rather than value comparisons.


#### 4. Correlated Subquery

Find students who scored the **highest marks in at least one course**.

* Demonstrates a subquery that depends on the **outer query values**.
* Useful to fetch max/min per group without `GROUP BY`.


#### 5. Subquery in `FROM` (Derived Table)

Calculate the **average marks per student** using a derived table.

* Demonstrates creating a **temporary result set** using a subquery in `FROM`.
* Useful for intermediate calculations that can be joined later.


#### 6. Nested Subquery (Multiple Levels)

Find students whose marks are above the **average of their department**.

* Demonstrates **multi-level nested subqueries**.
* Useful for comparing an entity against averages within groups.

---

## Summary

* Subqueries provide a **powerful way** to make queries more dynamic and analytical.
* Key types covered: **Scalar, IN, EXISTS, Correlated, Derived, and Nested Subqueries**.
* This task builds a strong foundation for writing **advanced analytical queries** in SQL.

---

## Outcome

- Gained hands-on practice with subqueries in different contexts (SELECT, WHERE, FROM).

- Understood scalar vs. correlated subqueries.

- Learned to filter and derive results efficiently using nested query logic.

- Built strong foundations for advanced SQL interview questions.
