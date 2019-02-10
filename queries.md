---
description: >-
  One of the core purposes of the SQL language is to retrieve information stored
  in a database. This is commonly referred to as querying. Queries allow us to
  communicate with the database by asking ques
---

# queries

## 

* `SELECT` is the clause we use every time we want to query information from a database.
* `AS` renames a column or table.
* `DISTINCT` return unique values.
* `WHERE` is a popular command that lets you filter the results of the query based on conditions that you specify.
* `LIKE` and `BETWEEN` are special operators.
* `AND` and `OR` combines multiple conditions.
* `ORDER BY` sorts the result.
* `LIMIT` specifies the maximum number of rows that the query will return.
* `CASE` creates different outputs.

## SELECT

 Let's only select the `name` and `genre`columns of the table.

```text
SELECT name, genre 
FROM movies;
```

## Alias

 It is important to remember that the columns have not been renamed in the table. The aliases only appear in the result.

```text
SELECT imdb_rating AS 'IMDB'
FROM movies;
```

## SELECT DISTINCT

 Filtering the results of a query is an important skill in SQL. It is easier to see the different possible `genre`s in the `movie` table after the data has been filtered than to scan every row in the table.

```text
SELECT DISTINCT year
FROM movies;
```

## WHERE

```text
SELECT *
FROM movies
WHERE year>=2014;

```

## LIKE

```text
SELECT * FROM movies
WHERE name LIKE 'Se_en';
```

```text
SELECt * FROM movies 
WHERE name LIKE 'The %';
```

## IS NULL/IS NOT NULL

```text
SELECT name FROM movies
WHERE imdb_rating IS NOT NULL;
```

## BETWEEN

* `BETWEEN` two letters _is not_ inclusive of the 2nd letter.
* `BETWEEN` two numbers _is_ inclusive of the 2nd number.

```text
SELECT * FROM movies
WHERE name BETWEEN 'D' AND 'G';
```

## AND

```text
SELECT * FROM movies
WHERE year BETWEEN 1990 AND 1999 AND genre='romance';
```

## OR

```text
SELECT * FROM movies
WHERE year >2014 OR genre='action';
```

## ORDER BY

* `DESC` is a keyword used in `ORDER BY` to sort the results in _descending order_ \(high to low or Z-A\).
* `ASC` is a keyword used in `ORDER BY` to sort the results in _ascending_ order \(low to high or A-Z\).

```text
SELECT * FROM movies 
WHERE imdb_rating >8
ORDER BY year DESC;
```

## LIMIT

```text
SELECT*FROM movies
ORDER BY imdb_rating DESC
LIMIT 3;
```

## CASE

 A `CASE` statement allows us to create different outputs \(usually in the `SELECT` statement\). It is SQL's way of handling [if-then](https://en.wikipedia.org/wiki/Conditional_%28computer_programming%29) logic.

```text
SELECT name,
CASE
WHEN imdb_rating >8 THEN 'Fantastic'
WHEN imdb_rating <6 THEN 'Poorly Received'
ELSE 'Avoid at All Costs'
END AS 'Review'
FROM movies;
```

