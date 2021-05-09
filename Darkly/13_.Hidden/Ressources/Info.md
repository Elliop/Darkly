<h1>Faille</h1>

Sur la page `http://10.12.100.25/robots.txt`

On va trouver un `/.hidden`

On va d'abord récupérer le dossier en local pour le but d'avoir un accès plus rapide et simple au dossiers et fichiers enfants:

`wget -r -np -e robots=off -R "index.html*" http://10.12.100.25/.hidden/`

Un dossier au nom de `10.12.100.25` est créé et contient le dossier `.hidden` ainsi que les dossiers et fichiers enfants de celui-ci.
Nous avons constaté que tout les dossiers contenaient un dossiers fils ou un fichier README.
Ces fichiers ont une phrases chacune nous indiquants que nous étions tombé sur le mauvais :

Nous avons donc pense que l'un des fichiers readme contenais le flag a trouver.
Nous avons donc fait la recherche d'un fichier contenant un chiffre (ici le 5) :
`grep -r "5" .*`

Ce qui va donner `99dde1d35d1fdd283924d84e6d9f1d820`

<h1>Explication de la commande </h1>

`-r` : recursive <br>
`-np` : permet de ne pas remonter dans les repertoires parents <br>
`-e` : Exécute commande comme si elle faisait partie de .wgetrc <br>
`-R` : spécifie la liste des suffixes ou modèles de noms de fichiers qui doivent être acceptés ou rejetés <br>

Sur ce points on a trouvé ce flag `99dde1d35d1fdd283924d84e6d9f1d820` mais j'ai remarqué que ce dernier n'est pas comme les 13 autres flag que ca soit au niveau de length ou structure donc j'ai essayer de décrypter le petit flag ce qui nous adonner le mot `findme` et ré appliquer un hash `sha256` pour trouver le flag finale.

<h1>Éviter cette faille</h1>

C'est bien d'avoir un /robots.txt mais il faut le proteger par un htaccess ou ne pas laisser ce genre d'information


<h1>Ressources</h1>

http://jp.barralis.com/linux-man/man1/wget.1.php

https://stackoverflow.com/questions/273743/using-wget-to-recursively-fetch-a-directory-with-arbitrary-files-in-it