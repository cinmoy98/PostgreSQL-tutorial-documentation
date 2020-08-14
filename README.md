🅿🅾🆂🆃🅶🆁🅴🆂🆀🅻

# PostgreSQL-tutorial-documentation
A complete walk through guide to master on PostgreSQL

[Follow me on LinkedIn](https://www.linkedin.com/in/cinmoys-here/)

This Documentation includes:
- [Introduction](#introduction)
- [Installation](#installation)
- [Getting Started](#your-first-step)
 - [Creating Database](#creating-database)
 - [Connect database](#connecting-to-database)
 - [Creating Table](#creating-table)
 - [Insert into](#insert-into)

> I used Windows 10 (64-bit) operating system to run all the codes and procedures.

# 🚧 Installation

Make sure your hard disk have enough space for installation.Then Download the installer file from the link.Download the latest version of your computer architecture.
> [Download from here(For windows users)](https://www.enterprisedb.com/downloads/postgres-postgresql-downloads)

Other operating system users can download from this [link](https://www.postgresql.org/download/)

Run the installer file.Installation process is like any other software but make sure you mark the following items correctly.
- PostgreSQL Server
- pgAdmin
- Stack Builder
- Command Line Tools

![alt text](images/insatallation.png)

After you finish you can run either `SQL Shell (psql)` for command line client or `pgAdmin 4` for GUI client.You are now ready to go.


# Your first step
As our pc serves as a server(database server) we need a client with which we can connect,view the contents and modify them. In Three ways we can do it.

- GUI client (`pgAdmin 4`)
- Terminal/cmd (`SQL Shell`)
- Application

I will use mostly terminal/cmd for my future works as it is a good habit and helps a lot during real projects.


Run the SQL Shell (psql).As you are running it for the first time your default server[localhost], Database [postgres], port [5432], Username [postgres].So you need to press just `enter`.Password is the superuser password that you set during installation.

<p align="center">
	<img src="https://i.ibb.co/L5KPXvs/getting-started.png" alt="getting-started" border="0">
</p>

For windows you can operate from `command prompt` also.You have to add the `PostgreSQL` bin directory in the system path (add in path under environment variables).
Open command prompt.Run-

`psql -U postgres`

provide your superuser password.You are done.😁 

## Creating database
Before starting things be familiar with the terminal environment and basic navigation commands.
Remember psql or SQL commands are not case sensetive.But you are advised to use the **UPPERCASE** letter in the commands. 

Run - 

`CREATE DATABASE test;`

## Connecting to database

You can connect a database in a various way.
- **Case 1**
 - You can simply use this command to connect a database `cinmoy` if user remains same : `\c cinmoy`
- **Case 2**
 - If credentials are different then: `\c DBNAME USER HOST PORT`
- **Case 3**
 - Or you can just connect from windows cmd : `psql DBNAME USER`

## Creating Table

To create a new table, you use the `CREATE TABLE` statement.
The following statement creates the `accounts` table:
```SQL

CREATE TABLE person (

	id BIGSERIAL NOT NULL PRIMARY KEY,
	first_name VARCHAR(50) NOT NULL,
	last_name VARCHAR(50) NOT NULL,
	gender VARCHAR(5) NOT NULL,
	date_of_birth DATE NOT NULL

);

```

**In this syntax:**

- Creating a table that already exists will result in a error. The IF NOT EXISTS option allows you to create the new table only if it does not exist. When you use the IF NOT EXISTS option and the table already exists, PostgreSQL issues a notice instead of the error and skips creating the new table.

- Specify a comma-separated list of table columns. Each column consists of the column name, the kind of data that column stores, the length of data, and the column constraint. The column constraints specify rules that data stored in the column must follow. For example, the not-null constraint enforces the values in the column cannot be NULL. The column constraints include not null, unique, primary key, check, foreign key constraints.

- Finally, specify the table constraints including primary key, foreign key, and check constraints.

> Note that some table constraints can be defined as column constraints like primary key, foreign key, check, unique constraints.Check them [here](https://www.postgresql.org/docs/9.4/ddl-constraints.html)

You can write this command in a line,like this:

<p align="center">
	<img src="https://i.ibb.co/f8Gb2c1/create-table1.png" alt="create-table1" border="0">
</p>

Or you can every colums seperately by pressing `enter` until a `;` is pressed:

<p align="center">
	<img src="https://i.ibb.co/0cdP604/create-table2.png" alt="create-table2" border="0">
</p>

Then to describe all the tables simply run `\d`

<p align="center">
	<img src="https://i.ibb.co/qWVnsFt/create-table3.png" alt="create-table3" border="0">
</p>

You can describe a table by `\d table_name`

<p align="center">
	<img src="https://i.ibb.co/pPQ2Xrf/create-table4.png" alt="create-table4" border="0">
</p>

## Insert Into

Insert into is so simple.Just specify the columns name you want to insert into and write the values accordingly.
- If you want to insert all column values then you don't need to write the columns name.

- If your column data type is `BIGSERIAL` then you don't need to write the column name.

**Example:**

```SQL

INSERT INTO person(first_name, last_name, gender, date_of_birth)
VALUES('Cinmoy Das', 'Shuvro', 'Male', '1890/01/08');

```

Column `id` is on autocompletion.It is being counted and inserted autometically.

Or, if you want to insert into all columns then,simply:

```SQL

INSERT INTO person
VALUES('Cinmoy Das', 'Shuvro', 'Male', '1890/01/08');

```

 <p align="center">
	<img src="https://i.ibb.co/qdwztQS/insert.png" alt="insert" border="0">
</p>


> 🔞 Adults always uses constraints.


## SELECT

Its simple for now but will be complex as we move on.

The basic command :

```SQL

SELECT column_1, column_2, ..... ,column_n FROM table_name;

```
If you want to select all columns from the table then-

```SQL

SELECT * FROM table_name;

```

 <p align="center">
	<img src="https://i.ibb.co/k3YzThB/selct.png" alt="selct" border="0">
</p>



## ORDER BY
- ASC (Ascending order(default))
- DESC (Descending order)

Basic format :

```SQL

SELECT column_1, column_2, ..., column_n FROM table_name ORDER BY
column_priority_1, column_priority_2, ... ,column_priority_n ASC/DESC; 

```
Example :

```SQL

SELECT * FROM person ORDER BY country_of_birth;

```
 <p align="center">
	<img src="https://i.ibb.co/0X5DSX3/order-asc.png" alt="order-asc" border="0">
</p>


```SQL

SELECT * FROM person ORDER BY country_of_birth DESC;

```
 <p align="center">
	<img src="https://i.ibb.co/m67nHS6/order-desc.png" alt="order-desc" border="0">
</p>


## DISTINCT

It fetches the unique values from a column.


```SQL

SELECT DISTINCT country_of_birth FROM person ORDER BY country_of_birth;

```
 <p align="center">
	<img src="https://i.ibb.co/BC3V9Yc/distinct.png" alt="distinct" border="0">
</p>



## WHERE, AND, OR

Ok its time move on to the real world.Because in the projects what you will need is to fetch query under certain condition.I will give you the basic example but things will get complex when you will get your hands dirty.

So, `WHERE` is used before certain conditions.Basic structure is-

```SQL

SELECT * FROM table_name WHERE conditions ;

```

So,lets take a example

```SQL

SELECT * FROM person WHERE country_of_birth = 'China';

```

It's time for some logic works. Yah you can use `AND` `OR` logics here too and why not?

> I am showing a relatively complex query.Hope you will understand it if you are familiar with basic programming

```SQL

SELECT * FROM person WHERE gender = 'Male' AND (country_of_birth = 'China' OR country_of_birth = 'Brazil');

```
<p align="center">
	<img src="https://i.ibb.co/PT5vQs1/where.png" alt="where" border="0">
</p>


## IN

So,first let me give a case - 

```SQL

SELECT * FROM person WHERE country_of_birth = 'China' OR country_of_birth = 'Poland' OR country_of_birth = 'Brazil' ; 

```

Look we have to write thrice the column name `country_of_birth` .What can we do ? 😫

You got it we can simply use `IN`

```SQL

SELECT * FROM person WHERE country_of_birth IN ('China', 'Poland', 'Brazil');

```

Pretty Simple, hah ? 😃
Don't woory it will be more easy soon ....

## BETWEEN , NOT BETWEEN
 
`BETWEEN` fetches data in a range.It can be applied on several data types.It's easy.Look at some examples :

```SQL

SELECT * FROM person WHERE date_of_birth BETWEEN DATE '1990-01-01' AND '1995-12-31' order by date_of_birth;

```
```SQL
SELECT * FROM person WHERE id BETWEEN 150 AND 200;
```

If you want to check if a value is out of a range, you combine the NOT operator with the `BETWEEN` operator as follows:

```SQL
SELECT * FROM person WHERE id NOT BETWEEN 150 AND 200;
```

> You often use the `BETWEEN` operator in the `WHERE` clause of a `SELECT`, `INSERT`, `UPDATE` or `DELETE` statement.

## LIKE

Sometimes we may require tuples from the database which match certain patterns. For example, we may wish to retrieve all columns where the tuples start with the letter ‘y’, or start with ‘b’ and end with ‘l’, or even more complicated and restrictive string patterns. This is where the LIKE Clause comes to rescue.

There are two kinds of wildcards used to filter out the results:

- % : Used to match zero or more characters. (Variable Length)
- _ : Used to match exactly one character. (Fixed Length)

The following are the rules for pattern matching with the LIKE Clause:

<p align="center">
	<img src="https://i.ibb.co/ydyyVMJ/like.png" alt="like" border="0">
</p>

Some examples:

```SQL
SELECT * FROM person WHERE email LIKE '%@reuters.com';
```
<p align="center">
	<img src="https://i.ibb.co/XLnW3QF/like2.png" alt="like2" border="0">
</p>

For case - insensetiveness you can use `ILIKE` clause.

Now try it out o your own .

## GROUP BY

The `GROUP BY` clause divides the rows returned from the `SELECT` statement into groups. For each group, you can apply an aggregate function e.g.,  `SUM()` to calculate the sum of items or `COUNT()` to get the number of items in the groups.
