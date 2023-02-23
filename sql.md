see the schema:
```sql
SELECT schema_name
FROM information_schema.schemata;
```

### psql
- [psql tips](https://psql-tips.org/)

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

run a local postgres db with docker, for testing:
```
docker run --name postgres-db -e POSTGRES_PASSWORD=docker -p 5432:5432 -d postgres 
```
connect to it:
```
psql -U postgres -h localhost -p 5432
```
