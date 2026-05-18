# AMA SESSION QUESTIONS AND ANSWERS:

## Adhikya Edammala: Difference between COUNT(*) and COUNT(col_name)

- `COUNT(*)` counts all rows in a table, including NULL values.
- `COUNT(col_name)` counts only non-NULL values in that column.

## Allanki VV Manikanta Sai: How to use global variable in a function

- Use the `global` keyword inside the function.

```
x = 10

def show():
    global x
    x = x + 5

show()
print(x)
```

## Arpit Yadav: Difference between Candidate Key and Primary Key

- Candidate Key: A column or set of columns that can uniquely identify rows.
- Primary Key: One candidate key selected as the main key of the table.

## Boorle Sowmya Sri Lakshmi: Explain about GROUPING SETS

- GROUPING SETS is used to generate multiple groupings in a single query.

```
SELECT dept, job, SUM(salary)
FROM emp
GROUP BY GROUPING SETS ((dept), (job));
```

## Injamuri Arun Kumar: Virtual Environment in Python

- A virtual environment is an isolated environment used to manage Python packages separately for different projects.

```
python -m venv myenv
```

## Kamparapu Lakshman: Difference between WHERE and HAVING

- WHERE filters rows before grouping.
- HAVING filters groups after GROUP BY.

## M Harivardhan Reddy: Fetch first five records from a table

```
SELECT * FROM table_name
LIMIT 5;
```

## Md Musharaf: Difference between CHAR and VARCHAR

- CHAR stores fixed-length strings.
- VARCHAR stores variable-length strings.

## Naman Sharma: Difference between DCL and TCL

- DCL (Data Control Language): Used for permissions (GRANT, REVOKE).
- TCL (Transaction Control Language): Used for transaction management (COMMIT, ROLLBACK).

## Nayunipatruni Harsha Vardhan: Difference between JOIN and UNION in SQL

- JOIN combines columns from multiple tables.
- UNION combines rows from multiple queries.

## Parlapalli Sulochana: How can we write multiple lines in a file in Python

```
lines = ["Hello\n", "Welcome\n", "Python\n"]

with open("file.txt", "w") as f:
    f.writelines(lines)
```

## Rongala Vasu: Aggregate function in Python

- Aggregate functions perform calculations on multiple values.
- Examples: sum(), max(), min(), len().

## Tumma Haritha: Method Chaining in Python

- Method chaining means calling multiple methods in a single statement.

## Vikas Mehta: Normalization in SQL

- Normalization is the process of organizing data to reduce redundancy and improve consistency.

## Yash Nitin Raut: Difference between SQL and MySQL

- SQL: A query language used to manage databases.
- MySQL: A relational database management system that uses SQL.
