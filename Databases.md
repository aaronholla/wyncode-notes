# Databases

SQL - any database that stores in tables in rows.

# ORM

Object relational Mapper

# ERD

A map of how all of the models in the database relate to each other.

A course has many students, a student belongs to a course.

# Relations

Primary Keys - a unique column that represents the row in the table  
Foriegn keys - a key on a table that maps to primary key on another table

referential integrety - cannot reference a primary key that does not exist.

Orphan records - records that don't have a reference parent  
Dependent Destroy - remove the orphans when parent goes away  
Dependent Null - set orphan to null when parent goes away

# Join Tables

Has many through - a table that has each id from multiple tables

Students Table
| id | students |
| --- | -------- |
| 1 | Andy |
| 2 | Aaron |

Enrollments Join Table

| id  | student_id | course_id |
| --- | ---------- | --------- |
| 1   | 1          | 1         |
| 2   | 1          | 2         |
| 2   | 2          | 3         |
| 2   | 1          | 2         |

Courses Table

| id  | title      |
| --- | ---------- |
| 1   | HTML       |
| 2   | CSS        |
| 3   | Javascript |
