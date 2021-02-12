## Django
Commands for working with a docker'd django app.

See the live logs:
```bash
heroku logs -a <app-name> -t
```

Access the Django shell:
```bash
heroku run python manage.py shell -a <app-name>
```

Dump data:
```bash
heroku run python manage.py dumpdata --natural-foreign --indent 2 \
\ -e contenttypes \
\ -e sessions \
\ <app-name> -- > fixtures.json
```
