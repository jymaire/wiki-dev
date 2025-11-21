# Généralités

Pour instancier une classe avec paramètres (comme on aurait un constructeur avec des paramètres en Java), il faut ajouter des paramètres à la méthode `__init__`

Exemple de https://docs.python.org/3/tutorial/classes.html#class-objects :
```
class Complex:
    def __init__(self, realpart, imagpart):
        self.r = realpart
        self.i = imagpart

x = Complex(3.0, -4.5)
x.r, x.i
```

# Les méthodes

On peut avoir 3 types de méthodes différentes :
- les méthodes "normales" ou "d'instances"
- les méthodes statiques
- les méthodes de classe

  ## Méthode d'instance

  Elle a pour premier paramètre `self` qui est l'instance de la méthode. Ce paramètre est obligatoire à la déclaration de la méthode mais facultatif à son appel.

  On appelle une méthode `m1` via son instance : `instance.m1()`

  ## Méthode statique

  C'est une méthode qui n'est pas liée à une instance de la classe et qui n'a pas de règle particulière sur ses paramètres.

  On appelle une méthode statique `s1` d'une classe `c1` comme cela : `c1.s1()`

  ## Méthode de classe

  C'est une méthode qui n'est pas liée à une instance de la classe et qui doit avoir comme premier paramètre sa classe. Ce paramètre est obligatoire à la déclaration de la méthode mais facultatif à son appel.

  On appelle une méthode statique `mc1` d'une classe `c1` comme cela : `c1.mc1()`

# Les scopes

When the definition of a function or class is nested (enclosed) within the definitions of other functions, its nonlocal scopes are the local scopes of the enclosing functions. 

Source : https://docs.python.org/3/reference/simple_stmts.html#nonlocal

The global statement applies to the entire current scope (module, function body or class definition). However, variables must still not be used or assigned to prior to their global declaration. 

Source : https://docs.python.org/3/reference/simple_stmts.html#global

Exemple de https://docs.python.org/3/tutorial/classes.html#scopes-and-namespaces-example 

```
def scope_test():
    def do_local():
        spam = "local spam"

    def do_nonlocal():
        nonlocal spam
        spam = "nonlocal spam"

    def do_global():
        global spam
        spam = "global spam"

    spam = "test spam"
    do_local()
    print("After local assignment:", spam)
    do_nonlocal()
    print("After nonlocal assignment:", spam)
    do_global()
    print("After global assignment:", spam)

scope_test()
print("In global scope:", spam)
```

The output of the example code is:

```
After local assignment: test spam
After nonlocal assignment: nonlocal spam
After global assignment: nonlocal spam
In global scope: global spam
```
