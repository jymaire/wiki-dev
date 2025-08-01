
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
