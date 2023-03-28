# Sql-Intro
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
