# Non-Correlated Subqueries

## Query inside query

```text
SELECT * FROM flights
WHERE origin in (SELECT code FROM airports
                WHERE elevation <2000);
```

