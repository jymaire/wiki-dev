

```
select(a)
.where(a.id == 1 and a.name == 'n')
```

ne fonctionne pas, il faut utiliser un opérateur `and_`

```
select(a)
.where(and_(a.id == 1, a.name == 'n'))
```
