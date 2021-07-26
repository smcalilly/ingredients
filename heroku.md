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

ssh into an app:
```bash
heroku run bash -a <app-name>
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

[load data](https://stackoverflow.com/questions/15041853/running-loaddata-on-heroku-without-adding-the-data-file-to-repository/49152992) to a heroku db, from a local file:
```bash
cat data.json | heroku run -no-tty -a <app-name> -- python manage.py loaddata --format=json -
```

create a superuser:
```bash
heroku run python manage.py createsuperuser -a <app-name>
```
