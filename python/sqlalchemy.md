# Lecture doc

https://docs.sqlalchemy.org/en/20/tutorial/index.html

## Engine

Le moteur est initialisé de manière lazy donc seulement à la première tâche demandée.

`echo=True` en paramètre de `create_engine` permet de logguer toutes les instructions SQL

source : https://docs.sqlalchemy.org/en/20/tutorial/engine.html

# Tips

```
select(a)
.where(a.id == 1 and a.name == 'n')
```

ne fonctionne pas, il faut utiliser un opérateur `and_`

```
select(a)
.where(and_(a.id == 1, a.name == 'n'))
```

----------------

`scalars().all()` pour récupérer des résultats propres
