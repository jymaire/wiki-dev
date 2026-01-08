

Pour voir la stack complète d’une exception en point d’arrêt si elle n’est pas présente : 

```
try:
  raise NotImplementedError("No error")
except Exception as e:
  exc_type, exc_obj, exc_tb = sys.exc_info()
  fname = os.path.split(exc_tb.tb_frame.f_code.co_filename)[1]
  print(exc_type, fname, exc_tb.tb_lineno)
```
et parcourir exc_tb pour avoir la stack complète


Dans Pytest, rajouter -s pour voir les “print”. On peut aussi utiliser "-k maRecherche" pour lancer tous les tests qui matchent "maRecherche".

Dans une assertion, on peut rajouter un message en cas d'erreur avec notamment ce qu'on a comparé 

` assert a == b,f"Assertion failed between {a} and {b}"`


`==` vérifie l'égalité alors que `is` compare l'adresse mémoire


-------------

`any` permet de vérifier qu'il y a au moins un élément dans la liste qui est True

`all`  permet de vérifier que tous les éléments de la liste sont True

-------------

Pour faire comme un Map en Java pour extraire juste une propriété dans une liste : 

`names = [client.name for client in clients]`

-------------- 

Fichier de type `pickle` pour sauvegarder des structures de données Python dans un fichier https://docs.python.org/3/library/pickle.html

--------------

On peut utiliser __slots__ pour optimiser la mémoire https://www.pythonmorsels.com/__slots__/

--------------

On peut forcer l'utilisation de paramètres nommées en rajouter `*,` au début

Par exemple

```
def get_name(*, id):
```

Ne pourra être appelé que 
```
get_name(id=1)
```
et pas

```
get_name(1)
```
---------------

On peut typer args et kwargs avec juste le type "contenu" https://adamj.eu/tech/2021/05/11/python-type-hints-args-and-kwargs/

--------------

Pour faire un mapper DTO -> Domain lorsqu'ils ont les mêmes noms d'attributs, on peut rajouter cette méthode dans la classe du  DTO

```
    @classmethod
    def from_domain(cls, domain: DomainClass) -> DTOClass:
        return cls(**{k: getattr(domain, k) for k in cls.__dataclass_fields__.keys()})
```
