### Équivalent de Map en Java

On peut utiliser le type `Record` en TS qui est l'équivalent d'une HashMap en Java https://www.typescriptlang.org/docs/handbook/utility-types.html#recordkeys-type 

### Destructuring

#### Tip 1

```
const obj1 = {
  prop1: '1',
  prop2: '2',
}

const obj2 = {
  prop3: '3',
  ...obj1,
}

```
va produire l'équivalent de 

```
const obj2 = {
  prop3: '3',
  prop1: '1',
  prop2: '2',
}

```

#### Tip 2
avec `data` l'objet suivant :
```
{
 'jwt' : 'ey...'
}`

```

si je fais : 

```
const { jwt: user_jwt } = data
```

À partir d'un objet `data`, je vais prendre l'attribut `jwt` et le stocker dans une variable `user_jwt`

#### Tip 3

```
const source = {
  email: 'aa@aa.fr',
  name : 'aza',
}

const { email, name } = source
```
Ce code va me produire deux variables `email` et `name` qui auront les valeurs de `source` (respectivement 'aa@aa.fr' et 'aza')

#### Tip 4

```
const name = 'aa'
const mail = 'aa@aa'

const total = {
  name,
  mail,
}
```
Ce code va me produire une variable `total` qui contient deux attributs. `name` qui a pour valeur 'aa' et `mail` qui a pour valeur 'aa@aa' 

Équivalent de
```
const total = {
  name: name,
  mail: mail,
}
```

### Interfaces

on peut rajouter des objets à une interface juste en la redéclarant
```
interface Point {
  x: number
}
// puis plus loin
interface Point {
  y: number
}
// alors Point contient x et y
``` 
