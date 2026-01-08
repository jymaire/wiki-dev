# Lecture doc

https://docs.sqlalchemy.org/en/20/tutorial/index.html

## Engine

Le moteur est initialisé de manière lazy donc seulement à la première tâche demandée.

`echo=True` en paramètre de `create_engine` permet de logguer toutes les instructions SQL

source : https://docs.sqlalchemy.org/en/20/tutorial/engine.html

## DBAPI

DBAPI est une interface pour interagir avec les BDD. C'est cette norme que les drivers de BDD vont devoir suivre.

Par défaut, une transaction est toujours en cours et un rollback est fait quand la connection est relachée. Il faut donc réaliser régulièrement des `commits`

Si on utilise `engine.begin()` au lieu de `engine.connect()` ça va commiter automatiquement à la fin de la transaction si il n'y a pas eu d'erreur.

Un select retourne un `Result` https://docs.sqlalchemy.org/en/20/core/connections.html#sqlalchemy.engine.Result .
Ce `Result` est un itérable qui contient des `Row` https://docs.sqlalchemy.org/en/20/core/connections.html#sqlalchemy.engine.Row .
Ce `Row` se comporte comme des `named tuples` https://docs.python.org/3/library/collections.html#collections.namedtuple .

La manière la plus "Pythonic" de lire les résultats est celle-là:

```
result = conn.execute(text("select x, y from some_table"))

for x, y in result:
    ...
```
Mais c'est loin d'être la seule manière de faire : https://docs.sqlalchemy.org/en/20/tutorial/dbapi_transactions.html#fetching-rows




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

------------------

Pour avoir la liste des colonnes retournées par une requête non typée, on peut utiliser `.keys()` sur un élément de la liste. (mais sinon un .mappings() après le execute c'est encore mieux
```
results = db.session.execute(statement).all()  # only for debug purposes

results[0].keys()

# ou mieux
results = db.session.execute(statement).mappings().all()  # only for debug purposes

```


----------------

`scalars().all()` pour récupérer des résultats propres
