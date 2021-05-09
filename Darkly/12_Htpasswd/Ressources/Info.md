<h1>Faille</h1>

Sur la page `http://10.12.100.25/robots.txt`

On va trouver un `/whatever`

Si on entre on aura un ndc et mot de passe en MD5

`root:8621ffdbc5698829397d97767ac13db3`

MD5 -> 8621ffdbc5698829397d97767ac13db3 -> dragon

Donc ndc:root et mdp:dragon

On peux utiliser le ndc et le mdp sur la page `http://10.12.100.25/admin` pour avoir le flag

<h1>Éviter cette faille</h1>

C'est bien d'avoir un /robots.txt mais il faut le proteger par un htaccess ou ne pas laisser ce genre d'information