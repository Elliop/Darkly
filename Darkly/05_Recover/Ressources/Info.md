<h1>Faille</h1>

Sur la page recover on voit une page un peu bizarre, un button de submit sans input
On Inspecte la page, on voit qu'il y a un input hidden qui contient une adresse mail
Pour avoir le flag il faut juste changer l'adresse mail et cliquer sur submit.

<h1>Éviter cette faille</h1>

Il ne faut surtout pas procéder de cette manière, on laissons ces informations c'est comme si on fait confiance à l'utilisateur donc il faut éviter de mettre ce genre d'infos dans les params d'un formulaire.