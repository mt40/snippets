# IntegrityError: duplicate key

Sometimes you can see an error like this when deploying a Django app:

```text
django.db.utils.IntegrityError: duplicate key value violates unique constraint "django_content_type_pkey"
DETAIL:  Key (id)=(2) already exists.
```

A possible reason is Postgres sequence is outdated. For example, table `django_content_type` has 3 rows but the `last_value` of sequence returns 2:

```sql
select * from django_content_type_id_seq;

+----------+-------+---------+
|last_value|log_cnt|is_called|
+----------+-------+---------+
|2         |0      |true     |
+----------+-------+---------+
```

We can fix this by:

```sql
SELECT setval('django_content_type_id_seq', (SELECT MAX(id) FROM django_content_type));
```

