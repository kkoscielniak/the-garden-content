---
title: MySQL Cheatsheet
---

_SQL_ (Structured Query Language) is a feature-rich language used for querying databases. These queries are better referred to as _statements_.

All of these examples are based on MySQL syntax.

## SELECT

Used to retrieve data from the database.

```sql
-- select all columns from the `users` table
SELECT * FROM users;

-- select `username` and `password` column from the `users` table
SELECT username, password FROM users;

-- select only 1 row from the `users` table
select * from users LIMIT 1;

-- select 1 row, but skip first two rows (effectively selecting 3rd row)
select * from users LIMIT 2,1;

-- select all columns from the `users` where the `username` col value is/is not `admin`
select * from users where username = 'admin';
select * from users where username != 'admin';

-- select the rows where the `username` is either `admin` or `jon`
select * from users where username='admin' or username='jon';

-- select the rows where the username is `admin` and `password` is `p4ssword`
select * from users where username='admin' and password='p4ssword';

-- [LIKE clause]
-- select any rows with username beginning with the letter a.
select * from users where username like 'a%';

-- select any rows with username ending with the letter n.
select * from users where username like '%n';

-- select any rows with a username containing the characters `mi` within them.
select * from users where username like '%mi%'

```

`

## UNION

The `UNION` statement combines the results of two or more `SELECT` statements to retrieve data from either single or multiple tables.

The `UNION` statement must retrieve the same number of columns in each `SELECT` statement, the columns have to be of a similar data type and the column order has to be the same.

```sql
-- select results from two tables and put them into one result set

SELECT name,address,city,postcode from customers UNION SELECT company,address,city,postcode from suppliers;

```

## INSERT

The `INSERT` statement tells the database we wish to add a new row of data into the table.

```sql
-- add username=bob, password=123 row into `users` table
insert into users (username,password) values ('bob','123');
```

## UPDATE

The `UPDATE` statement tells the DB we wish to update (alter) one or more rows of data within a table.

```sql
-- update `admin` username and password
update users SET username='root',password='pass123' where username='admin';
```

## DELETE

The **DELETE** statement tells the database we wish to delete one or more rows of data.

```sql
-- delete `admin` user
delete from users where username='martin';
```

Apart from missing the columns you wish to be returned, the format of this query is very similar to the `SELECT`. You can specify precisely which data to delete using the `WHERE` clause and the number of rows to be deleted using the `LIMIT` clause.

## Methods

### database()

Returns the db name

### group_concat(table_name)

Gets the specified column from multiple returned rows and puts it into one string separated by commas.

## information_schema

Contains information about all the databases and tables the user has access to.

```sql
SELECT 1,2,group_concat(table_name) FROM information_schema.tables WHERE table_schema = 'sqli_one'

SELECT 1,2,group_concat(column_name) FROM information_schema.columns WHERE table_name = 'staff_users'

SELECT 1,2,group_concat(username,':',password SEPARATOR '<br>') FROM staff_users
```
