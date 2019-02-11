---
description: Calculations performed on multiple rows of a table are called aggregates.
---

# aggregate funcions

* `COUNT()`: count the number of rows
* `SUM()`: the sum of the values in a column
* `MAX()`/`MIN()`: the largest/smallest value
* `AVG()`: the average of the values in a column
* `ROUND()`: round the values in the column

## COUNT

```text
SELECT COUNT(*) FROM fake_apps
WHERE price=0;
```

## SUM

 `SUM()` is a function that takes the name of a column as an argument and returns the sum of all the values in that column.

```text
SELECT SUM(downloads)FROM fake_apps;
```

## MAX/MIN

`MAX()` takes the name of a column as an argument and returns the largest value in that column. Here, we returned the largest value in the `downloads` column.

`MIN()` works the same way but it does the exact opposite; it returns the smallest value.

```text
SELECT MAX(downloads)FROM fake_apps;
SELECT MIN(downloads)FROM fake_apps;
```

## AVG

 SQL uses the `AVG()` function to quickly calculate the average value of a particular column.

```text
SELECT AVG (price)FROM fake_apps;
```

## ROUND

`ROUND()` function takes two arguments inside the parenthesis:

1. a column name
2. an integer

It rounds the values in the column to the number of decimal places specified by the integer.

```text
SELECT name,ROUND(price,0)FROM fake_apps;
another example:
SELECT ROUND(AVG(price),2)FROM fake_apps;
```

## GROUP BY

`GROUP BY` is a clause in SQL that is used with aggregate functions. It is used in collaboration with the `SELECT` statement to arrange identical data into _groups_.

The `GROUP BY` statement comes after any `WHERE`statements, but before `ORDER BY` or `LIMIT`.

```text
SELECT price,
COUNT(*)
FROM fake_apps
WHERE downloads>20000
GROUP BY price;
```

```text
SELECT category,
SUM(downloads)
FROM fake_apps
GROUP BY category;
```

SQL lets us use column reference\(s\) in our `GROUP BY` that will make our lives easier.

* `1` is the first column selected
* `2` is the second column selected
* `3` is the third column select

```text
SELECT category,
	price,
	AVG(downloads)
FROM fake_apps
GROUP BY 1,2;
```

## HAVING

 In addition to being able to group data using `GROUP BY`, SQL also allows you to filter which groups to include and which to exclude.

We can't use `WHERE` here because we don't want to filter the rows; we want to _filter groups_.

`HAVING` is very similar to `WHERE`. In fact, all types of `WHERE` clauses you learned about thus far can be used with `HAVING`.

```text
SELECT price,
	ROUND(AVG(downloads)),
  COUNT(*)
FROM fake_apps
GROUP BY 1
HAVING COUNT(price)>10;
```

* When we want to limit the results of a query based on values of the individual rows, use `WHERE`.
* When we want to limit the results of a query based on an aggregate property, use `HAVING`.

`HAVING` statement always comes after `GROUP BY`, but before `ORDER BY` and `LIMIT`.

```text
SELECT category,
	ROUND(AVG(downloads)),
  COUNT(*) AS 'ser'
FROM fake_apps
GROUP BY 1
HAVING COUNT(category)<15
ORDER BY 3 DESC
LIMIT 10;
```

















