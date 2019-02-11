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







