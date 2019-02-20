# Non-Correlated Subqueries

## IN - Query inside query

 A **non-correlated subquery** is a subquery that can be run independently of the outer query and can be used to complete a multi-step transformation.

Correlations on two tables:

```text
SELECT * FROM flights
WHERE origin in (SELECT code FROM airports
                WHERE elevation <2000);
```

```text
SELECT * FROM flights
WHERE origin IN (SELECT code FROM airports
                WHERE faa_region ='ASO');
```

Correlations on one table:

```text

```

