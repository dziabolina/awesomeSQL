---
description: >-
  One of the core purposes of the SQL language is to retrieve information stored
  in a database. This is commonly referred to as querying. Queries allow us to
  communicate with the database by asking ques
---

# queries

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

