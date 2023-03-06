---
id: 5gip04hh5zizpbpo4crkds7
title: SQL
desc: ''
updated: 1689194094796
created: 1649555235946
---
_ **Not in Anki **_  
SQL - structured query langage - standard language for communicating with relational dbs

dialect - flavor of SQL implementation unique to db mgt system

|Manipulate data	| Query Data	| Structure Data | Join Groupings
--------------- | ------------- | --------------- | -------------
INSERT	| SELECT	| CREATE TABLE	| INNER JOIN
UPDATE	|	| ALTER TABLE	| OUTER JOINS (LEFT, RIGHT)
DELETE	|	| DROP TABLE	| GROUP BY
	|    |	| ADD COLUMN	| SUM
	|    |	|DROP COLUMN	|COUNT
    
## Manipulating Data
- INSERT
    ``` SQL
    INSERT INTO table_name(field1, field2)
    VALUES(value1, value2)
    ```

- UPDATE
    ``` SQL
    UPDATE table_name
    SET column1 = value1, column2 = value2
    WHERE condition;
    ```

- DELETE
    ``` SQL
    DELETE FROM table_name WHERE condition;

## Querying Data
- SELECT
    ```SQL
    SELECT column1, column2
    FROM table_name;

## Structuring Data
### Create table
    ``` SQL
    CREATE TABLE table_name (
        column1 datatype,
        column2 datatype,
        column3 datatype
    );
    ```

### Alter table 
- adds, deletes, modifies columns in existing table; adds and drops variable constraints on existing table
	- DROP TABLE
		``` SQL
        ALTER TABLE table_name
		DROP TABLE table_name;
        ```
	- ADD COLUMN
        ``` SQL
		ALTER TABLE table_name
		ADD column_name datatype;
        ```
	- DROP COLUMN
    	``` SQL
        ALTER TABLE table_name
        DROP COLUMN column_name;
        ```
## Joins & Groupings
- JOIN is used to combine rows from 2 or more tables, based on related col
	- INNER JOIN, OUTER JOINS (LEFT, RIGHT)	
	- (INNER) JOIN: Returns records that have matching values in both tables
		``` SQL
        SELECT col_name.table, col_name.table
        FROM table1
        INNER JOIN table2 
        ON table1.col_name = table2.col_name;
        ```
	- LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
		``` SQL
        SELECT column_name(s)
		FROM table1
		LEFT JOIN table2
		ON table1.column_name = table2.column_name;
        ```
	- RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
		``` SQL
        SELECT column_name(s)
		FROM table1
		RIGHT JOIN table2
		ON table1.column_name = table2.column_name;
		```
	- FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table
		``` SQL
        SELECT column_name(s)
		FROM table1
		FULL OUTER JOIN table2
		ON table1.column_name = table2.column_name
		WHERE condition;
		```
- GROUP BY, SUM, COUNT - 
	- GROUP BY groups rows that have the same values into summary rows, like "find the number of customers in each country".
	- often used with aggregate functions (COUNT, MAX, MIN, SUM, AVG) to group the result-set by one or more columns.
		``` SQL
        SELECT column_name(s)
		FROM table_name
		WHERE condition
		GROUP BY column_name(s)
		ORDER BY column_name(s);
        ```
	
	From <https://www.w3schools.com/sql/sql_groupby.asp> 
