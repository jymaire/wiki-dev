### Destructuring

#### 1

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

#### 2
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
