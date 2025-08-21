
## Comment faire des appels HTTP avec un cookie défini

Écrire une requête dans l'outil `Tools/Http Request`

Puis ouvrir le fichier `http-client.cookies` pour rajouter des cookies (idéalement faire une première requête pour que l'outil ait déjà ajouté une ligne qu'on n'aura plus qu'à ajouter)

## Enchaîner plusieurs requêtes HTTP

Un exemple avec une authentification

```

POST http://localhost:8080/api/auth
Content-Type: application/json

{"email":"moi@here.fr","password":"secret password"}


###

GET http://localhost:8080/api/auth/check



```

`###` permet de faire la séparation entre deux requêtes.

On lance l'ensemble des requêtes avec le bouton "Run all requests in File" (double flèche verte)
