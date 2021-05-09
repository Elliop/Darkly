<h1>Faille</h1>

Sur la page `?page=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c`
on explorons un peu le code nous trouvons des commentaires `HTML` avec des informations
Pour avoir le flag il faut modifier le header `HTTP` de la requête (Il y a plusieurs méthode pour cela mais moi je vais utiliser la commande curl).

`curl --user-agent "ft_bornToSec" --referer https://www.nsa.gov/ http://10.12.100.25/index.php\?page\=e43ad1fdc54babe674da7c7b8f0127bde61de3fbe01def7d00f151c2fcca6d1c`

<h1>Explication de la commande </h1>

`--user-agent "ft_bornToSec" est un paramètre qui prendras le prochain argument comme user-agent, c'est à dire le nom du navigateur que nous voulons utiliser`

`--referer https://www.nsa.gov/ ce paramètre si, demanderas en arguments une url celle que nous voulons et qui serviras pour dire de quel site nous venons.`

<h1>Éviter cette faille</h1>

Pour éviter cette faille déjà il faut pas mettre des info en commentaires de la page car sur notre cas c'est grâce au commentaires qu'on a pu exploiter la faille sinon il faut créer la session correctement pour éviter les fuites.
