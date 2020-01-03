# Working with PostgreSQL from JavaScript

This document also includes non-javascript related notes.

## Return Rows as JSON

```sql
SELECT row_to_json(n)
FROM (
  SELECT id, name FROM contacts
) AS n
```
