# django

## interacting with the database:

[various ways to get all the table names](https://stackoverflow.com/questions/1845293/get-all-table-names-in-a-django-app#answer-1847330). i like this one:
```python
from django.db import connection
tables = connection.introspection.table_names()
seen_models = connection.introspection.installed_models(tables)
```

message in a template (works with bootstrap):
```
{% if messages %}
  {% for message in messages %}
    <div class="alert {% if message.tags %}alert-{{ message.tags }}{% endif %}" role="alert">
      <button type="button" class="close" data-dismiss="alert" aria-hidden="true">&times;</button>
      {{ message }}
    </div>
  {% endfor %}
{% endif %}
```
