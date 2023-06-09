# Sql-Intro fevey18158@duiter.com/SV5vGeFa43bpdxU
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
##################################################
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(60) NOT NULL, 
    department_id INT,
    CONSTRAINT fk_department FOREIGN KEY (department_id)
    REFERENCES departments(department_id)
); 

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(60) NOT NULL, 
    department_id INT,
    CONSTRAINT fk_department FOREIGN KEY (department_id)
    REFERENCES departments(department_id)
    ON DELETE SET NULL
    ON UPDATE CASCADE
); 

##################################################

ON DELETE and ON UPDATE
CASCADE: if a row in the parent table is deleted or updated, all matching rows will be deleted or updated automatically;
SET NULL: if a row in the parent table is deleted or updated, all matching foreign key values in the child table will be set to NULL;
RESTRICT: if we try to update or delete a row in the parent table, the operation will be rejected;
SET DEFAULT: if a row with the corresponding value is deleted or updated, the foreign key value in the child table will be set to the default value;
NO ACTION: this keyword can mean different actions depending on a dialect. In MySQL, it is equivalent to the RESTRICT keyword, so if we create the table employees with one of the queries above, delete and update actions in the table departments will be forbidden.

    ON DELETE SET NULL
    ON UPDATE CASCADE
    
##################################################
ALTER TABLE employees
ADD CONSTRAINT fk_department FOREIGN KEY (department_id)
REFERENCES departments(department_id);
###################################################
JetBrain Eg:

CREATE TABLE video_games (
	id INT Primary key,
    name varchar(50),
    game_genre varchar(45),
    game_developer varchar(50),
    release_date date
); 

CREATE TABLE game_developers (
	id INT Primary key,
    name varchar(50),
    address varchar(55),
    state varchar(50),
    city varchar(50),
    country varchar(50)
);  

CREATE TABLE platforms (
	id INT Primary key,
    name varchar(50),
    company_id varchar(55),
    company varchar(50),
    release_date date,
    original_price DECIMAL(9,2)
);  

CREATE TABLE platforms_games (
	game_id INT,
    platform_id INT,
    platform_name varchar(50),
    PRIMARY kEY (game_id, platform_id, platform_name),
	FOREIGN KEY (game_id) REFERENCES video_games(id),
    FOREIGN KEY (platform_id) REFERENCES platforms(id)
);  

CREATE TABLE characters (
	id INT Primary key,
    name varchar(50),
    birthday date,
    gender DECIMAL(2,1),
    info varchar(50)
);  

CREATE TABLE games_characters (
	character_id INT,
    character_name varchar(50),
    game_id INT,
    PRIMARY KEY (character_id, character_name, game_id),
    FOREIGN KEY (character_id) REFERENCES characters(id),
    FOREIGN KEY (gamesss_id) REFERENCES video_games(id)
);  
################################################################
    
