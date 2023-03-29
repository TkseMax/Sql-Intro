# Sql-Intro jasoya8836@djpich.com/SV5vGeFa43bpdxU
Sql Structured query Language 

Database is Structured data for fast retrieval by a pc

Database Management System (DBMS)
SQL = Relational Database Management System
In a nutshell, SQL is a querying language and MySQL is a database management service.
schemas and metadata - Schema describes how you organize the data. 
                       Metadata holds structural and statistical information.
##########
SELECT
  year, gender, COUNT(*) as cnt
FROM
  census
WHERE
  year BETWEEN 1920 and 2000
  AND name = 'Jessie'
GROUP BY
  year, gender
ORDER BY
  year, gender DESC
  
##########
SELECT * FROM Census;

Data Types - INTEGER, FLOAT, DECIMAL, VARCHAR, DATE, and BOOLEAN. REAL data type, REAL is FLOAT(24), or FLOAT of certain accuracy
DECIMAL(precision, scale) - Scale is the count of digits to the right of the decimal point.
                            Precision is the total count of digits in the number
FLOAT - has optional parameter n that specifies the precision and storage size (from 1 to 53) 
Varchar - VARCHAR(5). The strings orange and banana will exceed the length and will either truncate them or generate an error

###########
CREATE DATABASE students;

USE students;

CREATE TABLE students_info (
	student_id INT,
    name VARCHAR(30),
    surname VARCHAR(30),
    age INT
 );   
    
DROP DATABASE students;

SELECT * FROM students.students_info;
#############################################
ALTER TABLE employees 
ADD COLUMN employee_email VARCHAR(10);

ALTER TABLE employees 
MODIFY COLUMN employee_email VARCHAR(45); 

ALTER TABLE employees 
DROP COLUMN native_city; 

ALTER TABLE employees
CHANGE employee_email email VARCHAR(45); 
###########
