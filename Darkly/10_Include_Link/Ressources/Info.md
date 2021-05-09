<h1>Faille</h1>

On va exploiter une mauvaise utilisation de la fonction include() qui permet d'inclure une page dans une autre.
Il suffit de remonter directory apres directory en passant:
`http://10.12.100.25/index.php?page=../../../../../../../etc/passwd`

<h1>Éviter cette faille</h1>

Pour éviter cette faille il faut utiliser une redirection correct (peut etre utiliser `htaccess`)