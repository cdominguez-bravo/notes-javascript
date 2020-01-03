# Working with PostgreSQL from JavaScript

This document also includes non-javascript related notes.

## Return Rows as JSON

```sql
select row_to_json(n)
from (
  select id, name from contacts
) AS n
```
