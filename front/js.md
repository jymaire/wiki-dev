
## Chargement de script JS

Une fois que le navigateur a fini de charger le DOM, un événement DOMContentLoaded est envoyé. On peut l'écouter pour être sûr que le code JS ne sera exécuté qu'après le chargement de la page.

Sinon on peut placer l'import du fichier en bas de page pour être sûr qu'il soit lu après le chargement du DOM.

Dernière option : ajouter l'attribut `defer` à la balise script. Cela veut dire que le script sera lancé avant l'envoi de l'événement DOMContentLoaded mais après le chargement du DOM. C'est souvent cette option qui est recommandée.
