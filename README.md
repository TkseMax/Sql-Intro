# Sql-Intro jasoya8836@djpich.com/SV5vGeFa43bpdxU
Sql Structured query Language 

Database is Structured data for fast retrieval by a pc

Database Management System (DBMS)
SQL = Relational Database
schemas and metadata 
A schema describes how you organize the data. Metadata holds structural and statistical information.
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

Data Types - INTEGER, FLOAT, DECIMAL, VARCHAR, and BOOLEAN.
DECIMAL(precision, scale) - Scale is the count of digits to the right of the decimal point.
                            Precision is the total count of digits in the number
  
