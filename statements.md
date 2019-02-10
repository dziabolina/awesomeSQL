---
description: >-
  A statement is a string of characters that the database recognizes as a valid
  command.
---

# statements



* CREATE TABLE creates a new table.

```text
CREATE TABLE celebs (
   id INTEGER, 
   name TEXT, 
   age INTEGER
);

```

* INSERT INTO adds a new row to a table.

```text
INSERT INTO celebs (id, name, age)
VALUES (1, 'Justin Bieber', 22);
INSERT INTO celebs (id, name, age)
VALUES (2, 'Beyonce Knowles', 33);
INSERT INTO celebs (id, name, age)
VALUES (3, 'Jeremy Lin', 26);
INSERT INTO celebs (id, name, age)
VALUES (4, 'Taylor Swift', 26);
```

* SELECT queries data from a table.

```text
SELECT *
FROM movies
WHERE year>=2014;
```

* ALTER TABLE changes an existing table.

```text
ALTER TABLE celebs 
ADD COLUMN twitter_handle TEXT;
```

* UPDATE edits a row in a table.

```text
UPDATE celebs 
SET twitter_handle = '@taylorswift13' 
WHERE id = 4;
SELECT * FROM celebs;

```

* DELETE FROM deletes rows from a table.

```text
DELETE From celebs
WHERE id=1;
```

