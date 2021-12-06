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

get the types for a table:
```
\dT+ action.action_status
```
see https://stackoverflow.com/a/9537078
