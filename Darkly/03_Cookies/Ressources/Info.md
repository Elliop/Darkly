<h1>Faille</h1>
 
- On ouvert les outils de développement pour voir les Cookies stockés
- Voilà on a trouvé un Cookie I_am_admin avec une valeur `hash`
- C'est un hash MD5, décrypté le hash est la valeur correspondait à `false`
- On crypte en MD5 `true` et on a remplacé la valeur du Cookie
 
<h1>Éviter cette faille</h1>
 
Pour résoudre cette faille il faut au moins bien crypter la valeur des cookies et ajouter une date d'expiration, mais le mieux c'est d'éviter d'enregistrer des informations trop importantes de type admin etc.
