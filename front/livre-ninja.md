
Rest operator : `...` permet de déclarer un nombre variable de paramètres dans une fonction (à ne pas confondre avec le Spread operator qui permet d'éclater un tableau)

Rest : `function addPonies(...ponies)`

Spread : `const [winner, ...losers] = poniesInRace;`

Passage d'un paramètre optionnel dans une fonction : mettre un point d'interrogation à la fin de son nom `function addPointsToScore(player: HasScore, points?: number): void {`

Partial : si on veut créer une classe B à partir d'une classe A avec tous les attributs de A qui soient optionnels, on peut utiliser le type Partial de Typescript https://www.typescriptlang.org/docs/handbook/utility-types.html#partialtype 

Les imports : les imports en tout début de fichier servent pour le code TS et les imports dans l'annotation @Component servent pour le template HTML (CommonModule à importer pour les fonctionnalités standards d'Angular) NB : l'import dans l'annotation @Component a besoin de l'import en haut du fichier TS.

Signaux : considérer le contenu d'un Signal comme quelque chose d'immuable et bien utiliser la méthode "update" pour faire une mise à jour (et non pas "set") pour qu'Angular détecte bien qu'il y a eu un changement au sein de l'objet (si remplacement total d'un objet, on peut utiliser "set")

Dans l'exemple suivant, `selected` est un attribut de la balise `option`. Dans ce cas, la seule présence de l'attribut `selected` déclenchera son effet (peu importe si on lui affecte une valeur)
```
<option selected>apple</option>
<option selected="false">apple</option> <!-- quand même sélectionné-->

```
Les attributs sont liés à des éléments HTML (dans le code), par exemple un balise input. Puis, le navigateur va créer le DOM avec un noeud ici HTMLInputElement qui lui va avoir des propriétés. L'avantage de passer par les propriétés, c'est qu'on va mettre à jour le DOM. Une propriété est définie entre crochets [ ]. Par exemple, Angular permet de faire
```
<option [selected]="isSelected()" value="apple">Apple</option>
```
On peut aussi accéder à des propriétés de l'élément du DOM
```
<option [style.color]="couleurTexte()" value="apple">Apple</option>
```

NB : Angular utilise les propriétés sans les crochets ! donc les deux notations sont équivalentes dans un composant Angular
```
<ang-comp name="{{ person().name }}" />
<ang-comp [name]="person().name" />
```

Boucle for : il existe une annotation @empty pour gérer le cas d'une liste vide. Il existe les variables suivantes : $index (index élément courant), $first et $last (des booléens)

Les inputs sont passés après que le composant soit construit donc pas possible de les lire dans le constructeur.

ngOnChanges est appelé quand un input est modifié. En paramètre, on va avoir l'ancienne et la nouvelle valeur (ainsi qu'une méthode `isFirstChange()`)

ngOnInit est appelé après le 1er appel de ngOnChanges.

Un `effet` (signal de type `effect`) doit être créé dans le constructeur du composant (possible ailleurs mais plus complexe)

Un pipe async va gérer automatiquement la désouscription à un observable. On peut stocker le résultat dans une variable avec le mot clé `as` (par exemple : `@if (asyncUser | async; as user)`
