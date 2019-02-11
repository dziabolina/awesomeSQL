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











