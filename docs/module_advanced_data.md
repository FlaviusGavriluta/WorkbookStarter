# Advanced Data module

## General SQL

### What are relational databases? Explain the theory behind them!
* Relational Databases are a type of database that organize date into tables.
* Each table consists of rows and columns, where each column represents a different attribute and each row represents a single record.
* Relational databases use tables to represent entities and the relationships between them, and this relationships are defined through:
	* Primary Key: A unique identifier for each record in a table.
	* Foreign Key: A field that creates a relationship by referencing a primary key in another table.
* Examples of relational databases include MySQL, PostgreSQL, Oracle, SQL Server, etc.
* To illustrate a relational database, consider a database for a library. You might have two tables: one for books and one for authors.
  * The "Books" table could look like this:
  
	| ID | Title                  | Author_ID |
	|----|------------------------|-----------|
	| 1  | "Pride and Prejudice"  | 101       |
	| 2  | "War and Peace"        | 102       |
	| 3  | "Crime and Punishment" | 103       | 

   * And the "Authors" table could look like this:
	
	| ID  | NAME              |
	|-----|-------------------|
	| 101 | Jane Austen       |
	| 102 | Leo Tolstoy       |
	| 103 | Fyodor Dostoevsky |

### Why SQL is important these days?

### All the new GUI tools enable me to click a button to write SQL. Why should I spend time learning to write SQL manually?

### If SQL is standardized, should you be able to program with SQL on any databases?

### What makes SQL a nonprocedural language?

### What can you do with SQL?

---

## DQL

### Do the following statements return the same or different output? Why?

```sql
SELECT * FROM CHECKS;
select * from checks;
```

### The following queries do not work when entered into the command line psql console. Why not?

```sql
Select *
Select * from checks
Select amount name payee FROM checks;
```

### What shorthand could you use instead of `WHERE a >= 10 AND a <=30`?

### Which function capitalizes the first letter of a character string and makes the rest lowercase?

### Will this query work? Why?

```sql
SELECT COUNT(LASTNAME) FROM CHARACTERS;
```

### Assuming that they are separate columns, which function(s) would splice together FIRSTNAME and LASTNAME?

### Why are so few functions defined in the ANSI standard and so many defined by the individual implementations?

### What is the function of the GROUP BY clause?

### When using the HAVING clause, do you always have to use a GROUP BY also?

### Can you use ORDER BY on a column that is not one of the columns in the SELECT statement?

---

## Joins

### Explain the different kind of joins! (outer, inner, left, right, natural, etc.)

### How many tables can you join on?

### Would it be fair to say that when tables are joined, they actually become one table?

### How many rows would a two-table join produce if one table had 50,000 rows and the other had 100,000?

### What type of join appears in the following SELECT statement?

```sql
select e.name, e.employee_id, ep.salary  
from employee_tbl e, employee_pay_tbl ep  
where e.employee_id = ep.employee_id;
```

### In joining tables are you limited to one-column joins, or can you join on more than one column?

---

## DML

### Does SQL have a statement for file import/export operations?

### Can you copy data from a table into itself using the INSERT command? You would like to make duplicate copies of all the existing records and change the value of one field.

### What would happen if you issued the following statement?

```sql
DELETE * FROM COLLECTION;
```

### Can you remove columns with the ALTER TABLE statement?

### Is the DROP TABLE command functionally equivalent to the DELETE FROM <table_name> command?

### What is the difference between the functionality of the DELETE FROM <table_name> and the TRUNCATE TABLE command?

### When a table is created, who is the owner?

### If data in a character column has varying lengths, what is the best choice for the data type?
