#  SQL readingß

Relational Databases include a number of related tables with a fixed number of named columns. Using SQL syntax we can select data from the tables, directly or by cross referencing with another table. Tables can be added, altered and deleted and rows can be inserted, updated and deleted. Simple and complex queries can be made in order to pull or place the precise data that is required.

## Queries

- `SELECT` query database
- `WHERE` constrain results
- `AND` and `OR` logical keywords
- `=` `!=` `<` `<=` `>` `>=` conditional boolean operators
- `LIKE` and `NOT LIKE`
  - `%` matches sequence of zero or more characters
  - `_` matches a single character
- `BETWEEN` x `AND` y 
- `NOT BETWEEN` x `AND` y
- `IN(`x,y,z`)`
- `NOT IN(`x,y,z`)`
- `DISTINCT` limits duplicate results
- `ORDER BY` for 
  - Can be used with `ASC` and `DESC`
- `LIMIT` limit the results to specified count
- `NULL`
- `ON` used to connect tables during join
- `AS` aliasing an expression during a selection
- `COUNT(column)` or `COUNT(*)` counts the rows in a group or column
- `MIN(column)` returns smallest numerical value in column
- `MAX(column)` returns largest numerical value in column
- `AVG(column)` returns the average numerical value in column
- `SUM(column)` returns the sume of all numerical value in column
- `GROUP BY` use after `WHERE` to combine results of the specified column
- `HAVING` use after `GROUP BY` to apply additional constraints


### Example Queries from SQLBolt tutorial

Simple Selection:
``` sql
SELECT my_column, my_column_2
FROM my_table;
```


Selection with constraints:
```sql
SELECT my_column, my_column_2
FROM my_table
WHERE condition
    AND/OR another_condition;
```

Sorting, limiting and offsetting:
```sql
SELECT my_column, my_column_2
FROM my_table
WHERE condition(s)
ORDER BY my_column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

Adding table Joins:
```sql
SELECT my_column, my_column_2
FROM my_table
INNER/LEFT/RIGHT/FULL JOIN another_table 
    ON my_table.id = another_table.id
WHERE condition(s)
ORDER BY my_column, ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

Complete query demonstrating proper order of execution:
```sql
SELECT DISTINCT my_column, AGG_FUNC(column_or_expression), …
FROM my_table
    JOIN another_table
      ON my_table.column = another_table.column
    WHERE constraint_expression
    GROUP BY my_column
    HAVING constraint_expression
    ORDER BY my_column ASC/DESC
    LIMIT count OFFSET COUNT;
```

## Destructive Statements

- `INSERT INTO`
- `VALUES`
- `UPDATE`
- `SET` 
- `DELETE`
- `CREATE TABLE` or `CREATE TABLE IF NOT EXISTS`
- `ALTER TABLE`
- `ADD` adding columns
- `DEFAULT` set default data type for row
- `DROP` for column 
- `DROP TABLE` 
- `RENAME TO`
  
Data Types for SQL rows:
- `INTEGER`
- `BOOLEAN`
- `FLOAT`
- `DOUBlE`
- `REAL`
- `CHARACTER(NUM)`
- `VARCHAR(NUM)`
- `TEXT`
- `DATE`
- `DATETIME`
- `BLOB`

Table Constraints:
- `PRIMARY KEY`
- `AUTOINCREMENT`
- `UNIQUE`
- `NOT NULL`
- `CHECK(EXPRESSION)`
- `FOREIGN KEY`

### Example Statements from SQLBolt tutorial

Add Rows Explicitly:
```sql
INSERT INTO my_table
(my_column, another_column, …)
VALUES (value_or_expr, another_value_or_expr, …),
      (value_or_expr_2, another_value_or_expr_2, …),
      …;
```
Update Rows
```sql
UPDATE my_table
SET my_column = value_or_expr, 
    other_column = another_value_or_expr, 
WHERE condition;
```

Delete Rows
```sql
DELETE FROM my_talble
WHERE condition
```

Creating Tables
```sql
CREATE TABLE IF NOT EXISTS my_table (
    my_column DataType TableConstraint DEFAULT default_value,
    another_column DataType TableConstraint DEFAULT default_value;
```

Altering Tables (add column)
```sql
ALTER TABLE my_table
ADD my_column DataType OptionalTableConstraint 
    DEFAULT default_value;
```

Dropping Tables
```sql
DROP TABLE IF EXISTS my_table;
```
