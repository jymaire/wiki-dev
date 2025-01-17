
Rest operator : `...` permet de déclarer un nombre variable de paramètres dans une fonction (à ne pas confondre avec le Spread operator qui permet d'éclater un tableau)

Rest : `function addPonies(...ponies)`

Spread : `const [winner, ...losers] = poniesInRace;`

Passage d'un paramètre optionnel dans une fonction : mettre un point d'interrogation à la fin de son nom `function addPointsToScore(player: HasScore, points?: number): void {`

Partial : si on veut créer une classe B à partir d'une classe A avec tous les attributs de A qui soient optionnels, on peut utiliser le type Partial de Typescript https://www.typescriptlang.org/docs/handbook/utility-types.html#partialtype 

Les imports : les imports en tout début de fichier servent pour le code TS et les imports dans l'annotation @Component servent pour le template HTML (CommonModule à importer pour les fonctionnalités standards d'Angular) NB : l'import dans l'annotation @Component a besoin de l'import en haut du fichier TS.

Signaux : considérer le contenu d'un Signal comme quelque chose d'immuable et bien utiliser la méthode "update" pour faire une mise à jour (et non pas "set") pour qu'Angular détecte bien qu'il y a eu un changement

Dans l'exemple suivant, `selected` est un attribut de la balise `option`. Dans ce cas, la seule présence de l'attribut `selected` déclenchera son effet (peu importe si on lui affecte une valeur)
```
<option selected>apple</option>
<option selected="false">apple</option> <!-- quand même sélectionné-->

```
