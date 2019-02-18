---
description: >-
  Combining tables manually is time-consuming. Luckily, SQL gives us an easy
  sequence for this: it's called a JOIN.
---

# multiple tables

## JOIN

```text
SELECT * FROM orders
JOIN subscriptions
ON orders.subscription_id=subscriptions.subscription_id;

SELECT*
FROM orders
JOIN subscriptions
ON orders.subscription_id=subscriptions.subscription_id
WHERE subscriptions.description='Fashion Magazine';
```

 When we perform a simple `JOIN` \(often called an _inner join_\) our result only includes rows that match our `ON` condition.

checking row count for 2 tables and for joined table

```text
SELECT count(*)FROM newspaper;
SELECT COUNT(*)FROM online;
SELECT count(*)
FROM newspaper
JOIN online
ON newspaper.id=online.id;
```

## LEFT JOIN

```text
SELECT *
FROM newspaper
LEFT JOIN online
ON newspaper.id=online.id;
```

```text
SELECT*
FROM newspaper
LEFT JOIN online
ON newspaper.id=online.id
WHERE online.id IS NULL;
```

## CROSS JOIN

```text
SELECT *
FROM newspaper
CROSS JOIN months
WHERE start_month <= month
AND end_month >= month;
```

```text
SELECT month,
COUNT(*) AS 'subscribers'
FROM newspaper
CROSS JOIN months
WHERE start_month <= month
AND end_month >= month
GROUP BY month;
```

## UNION

 Sometimes we just want to stack one dataset on top of the other. Well, the `UNION` operator allows us to do that.

SQL has strict rules for appending data:

* Tables must have the same number of columns.
* The columns must have the same data types in the same order as the first table.

```text
SELECT*
FROM newspaper
UNION
SELECT *
FROM online;
```

## WITH

 Often times, we want to combine two tables, but one of the tables is the result of another calculation.

```text
WITH previous_query AS(
SELECT customer_id,
   COUNT(subscription_id) AS 'subscriptions'
FROM orders
GROUP BY customer_id)
SELECT customers.customer_name,
previous_query.subscriptions
FROM previous_query 
JOIN customers
ON  previous_query.customer_id=customers.customer_id;
```









