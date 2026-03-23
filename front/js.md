

# Suivi du cours Frontend mentors 

https://www.frontendmentor.io/learning-paths/javascript-fundamentals-oR7g6-mTZ-/article/660eb6a32f40450f917475d1/read


## Chargement de script JS

Une fois que le navigateur a fini de charger le DOM, un événement DOMContentLoaded est envoyé. On peut l'écouter pour être sûr que le code JS ne sera exécuté qu'après le chargement de la page.

Sinon on peut placer l'import du fichier en bas de page pour être sûr qu'il soit lu après le chargement du DOM.

Dernière option : ajouter l'attribut `defer` à la balise script. Cela veut dire que le script sera lancé avant l'envoi de l'événement DOMContentLoaded mais après le chargement du DOM. C'est souvent cette option qui est recommandée.

## DOM

Le DOM est une représentation en JS du document HTML.

`getElementById` est la manière la plus efficace de retrouver un élément dans le DOM. Par exemple, pour trouver les boutons dans un container, il est préférable de récupérer le container via son ID puis de chercher à l'intérieur ses boutons plutôt que d'utiliser un `querySelectorAll` qui fonctionnera aussi mais sera moins efficace.

```
// Good
const container = document.getElementById('container'); 
const buttons = container.querySelectorAll('button');

// Not so good, searching all over the DOM
const buttons = document.querySelectorAll('#container buttons'); 
```

`document.querySelector('p')` va récupérer la première balise p.

Pour ajouter une classe CSS sur un élément, on le fait avec `monElement.classList.add('className')` (remove et toggle existent aussi)
