---
title: MySQL Cheatsheet
draft: true
---
- `SELECT DISTINCT` - brings unique values from the table

```mysql
SELECT `name`, unit_price, unit_price * 1.1 as `new_price` FROM products
```

In SQL we need to use quotes when using dates (eg. in `WHERE`)

```mysql
SELECT * FROM sql_store.orders WHERE order_date > '2017-01-01';
```

in `WHERE` the `AND` operator takes precedence over the `OR` operator (it's evaluated 1st). It can be a,tered with parentheses

```mysql
SELECT * FROM sql_store.order_items WHERE order_id = 6 AND quantity * unit_price > 30
```

## `IN` operator
```mysql
SELECT * FROM [...]
WHERE state IN ('GA', 'MW', 'NY')
```
czyli `WHERE state = 'GA' OR state = 'MW' OR state = 'NY'`

```sql
SELECT * FROM sql_inventory.products WHERE quantity_in_stock IN (49, 38, 72)
```

## `BETWEEN` operator
```sql
WHERE points > 1000 AND points < 3000
```

```sql
WHERE points BETWEEN 1000 AND 3000
```

```sql
SELECT * FROM sql_store.customers 
WHERE birth_date BETWEEN '1990-01-01' AND '2000-01-01' 
```

## `LIKE` operator
- `%` - any number of characters
	- `b%` - starts with _b_ and then any number of characters
- `_` - single character

```sql
SELECT * FROM sql_store.customers WHERE phone LIKE '9%' OR address LIKE '%trail%';
```

```sql
SELECT * FROM sql_store.customers WHERE phone LIKE '9%'
```

Can be combined with `NOT`

## `REGEXP` operator
Practically like `LIKE` but allows to use regular expression

## `IS NULL`

---
Cheat sheet

- Select 