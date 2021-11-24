see the schema:
```sql
SELECT schema_name
FROM information_schema.schemata;
```

### psql
standard `\dt` command doesn't show everything
```
\dt *.*
```

do a select that doesn't show any data but only the column names:
```
-S
```

