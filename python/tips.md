

Pour voir la stack complète d’une exception en point d’arrêt si elle n’est pas présente : 

```
try:
  raise NotImplementedError("No error")
except Exception as e:
  exc_type, exc_obj, exc_tb = sys.exc_info()
  fname = os.path.split(exc_tb.tb_frame.f_code.co_filename)[1]
  print(exc_type, fname, exc_tb.tb_lineno)
```


Dans Pytest, rajouter -s pour voir les “print”

Dans une assertion, on peut rajouter un message en cas d'erreur avec notamment ce qu'on a comparé 

` assert a == b,f"Assertion failed between {a} and {b}"`


`==` vérifie l'égalité alors que `is` compare l'adresse mémoire


-------------

`any` permet de vérifier qu'il y a au moins un élément dans la liste qui est True

`all`  permet de vérifier que tous les éléments de la liste sont True

-------------

Pour faire comme un Map en Java pour extraire juste une propriété dans une liste : 

`names = [client.name for client in clients]`
