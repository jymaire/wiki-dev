
Rest operator : `...` permet de déclarer un nombre variable de paramètres dans une fonction (à ne pas confondre avec le Spread operator qui permet d'éclater un tableau)

Rest : `function addPonies(...ponies)`

Spread : `const [winner, ...losers] = poniesInRace;`

Passage d'un paramètre optionnel dans une fonction : mettre un point d'interrogation à la fin de son nom `function addPointsToScore(player: HasScore, points?: number): void {`
