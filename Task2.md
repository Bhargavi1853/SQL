# INSERTING DATA AND NULL HANDLING
# 📥 Data Insertion Description
The database student_attendance_system was successfully used to populate initial data across all core tables using INSERT INTO statements:

🔹 Department Table

- Inserted 2 departments:

    - 1 → Computer Science

    - 2 → Mechanical

🔹 Student Table

- Inserted 2 students:

    - 101 → bala, Email: bala@gmail.com, Department: Computer Science

    - 102 → bhargavi, Email: bhargavi@gmail.com, Department: Mechanical

🔹 Course Table

- Inserted 4 courses:

    - DBMS, Thermodynamics, and two C courses offered by both departments.

🔹 Class Table

- Added 4 class sessions linked to the above courses:

    - Each with a course ID, date, and assigned faculty (e.g., Prof. Ramesh, Asst. Sai Kumar)

🔹 Attendance Table

- Recorded student attendance for specific classes:

    - Each entry includes student ID, class ID, and attendance status (present or absent).

<img width="1870" height="805" alt="Inserting Data" src="https://github.com/user-attachments/assets/b7555331-6aae-458f-b30b-dab0916b728d" />

All insertions were successful with zero warnings or duplicate entries. The data is now ready for further manipulation using UPDATE, DELETE, and NULL handling operations.


# 📊 Viewing Inserted Data (Select Queries)
After inserting values into all tables, the following SELECT * FROM table_name; commands were executed to verify the contents of the database.

<img width="578" height="861" alt="Results of inserting data" src="https://github.com/user-attachments/assets/c1b2b26d-0fc5-4c84-acea-8dd0564f73e4" />

This confirms that the data was successfully inserted and reflects correct relationships between entities in the student attendance system.


# 🔁 Update & Delete Operations
This section showcases how records in the attendance, student, and course tables are updated or deleted using SQL statements.

✅ Update Operations

Updating Attendance Status

    - UPDATE attendance SET status = 'present' WHERE atd_id = 402;
- Updates the status of the record with atd_id = 402 from 'absent' to 'present'.

Updating Student Email

    - UPDATE student SET std_email = 'bala05@gmail.com' WHERE std_id = 101;
- Changes the email of student 101 to 'bala05@gmail.com'.

❌ Delete Operations with Constraints

Deleting a Course Record

    - DELETE FROM course WHERE course_id = 204;
- Failed due to foreign key constraint: The course is referenced in the class table.

Deleting Courses by Department

    - DELETE FROM course WHERE dept_id = 2;
- Failed for the same reason — courses from department 2 are referenced elsewhere.

✅ Successful Delete

Deleting an Attendance Record

    - DELETE FROM attendance WHERE atd_id = 404;
- Successfully removed the record for atd_id = 404 since it was not referenced by any other table.

<img width="1890" height="294" alt="Updating and Deleting" src="https://github.com/user-attachments/assets/c869b293-3238-4e96-9b97-a351b9ea0879" />


⚠️ Notes:

- Foreign Key Constraints prevent deleting rows that are being referenced in other tables (like class referencing course).

- To safely delete such records, dependent rows must be removed first (e.g., delete class entries before deleting a course).

- This confirms the integrity enforcement of the relational model in your student attendance system.


# ⚠️ 4. NULL Handling

🔹 Inserting a student without email (nullable column):

    - INSERT INTO student (std_id, std_name, std_email, dept_id) VALUES (103, 'Maze', NULL, 1);

🔹 Try inserting NULL in status (non-nullable, will cause error):

-- This should fail (for learning)
    
    -INSERT INTO attendance (atd_id, std_id, class_id, status) VALUES (405, 103, 301, NULL);

🔹 Optional: Add a student with missing department (NULL foreign key):

    - INSERT INTO student (std_id, std_name, std_email, dept_id) VALUES (104, 'Akhil', 'akhil@gmail.com', NULL);

-- To see the changes Which are done upto now

    - SELECT * FROM attendance;
    - SELECT * FROM student;

<img width="617" height="399" alt="Updated Tables" src="https://github.com/user-attachments/assets/1163519b-6051-44e5-a28a-b3d0ac4a011a" />

To check if all records reflect your operations correctly.
