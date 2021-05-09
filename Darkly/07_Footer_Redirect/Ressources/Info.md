<h1>Faille</h1>

Dans le footer il y a logos de réseaux sociaux qui redirigent vers le site officiel du logo, mais la manière dont cette redirection est faite est une faille qui peut être exploitée pour rediriger vers un autre site pour faire du phising
pour avoir le flag il faut changer le lien de redirection par n'import quel site par exemple

`href="index.php?page=redirect&site=intra"`

<h1>Éviter cette faille</h1>

Pour se protéger de cette faille, nous pouvons écrire l'url du site directement sans passer par une autre page de notre site qu'elle fera la redirection.
