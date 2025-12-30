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

``` o const { jwt: intercom_user_jwt } = data
```


partir d'un objet `data` q
