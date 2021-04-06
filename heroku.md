## Heroku CLI
See the live logs:
```bash
heroku logs -a <app-name> -t
```

create a postgres add-on:
```bash
heroku addons:create heroku-postgresql:hobby-dev
```

set the stack as a container for your app:
```bash
heroku stack:set container
```

## Django
Commands for working with a docker'd django app.

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

create a superuser:
```bash
heroku run python manage.py shell -a <app-nam>
```
