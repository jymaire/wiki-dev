Item 1 :

Si on créé une classe immuable (cf item 15) alors utiliser `equals` ou `==` est équivalent sémantiquement. Mais utiliser `==` est meilleur en terme de performances. 
(raison de la règle Sonar sur les énumerations https://github.com/SonarSource/sonar-java/blob/master/java-checks/src/main/java/org/sonar/java/checks/EnumEqualCheck.java )

Item 8 :

Dans les constructeurs privés, on peut lancer une https://docs.oracle.com/javase/8/docs/api///?java/lang/AssertionError.html pour s'assurer que personne n'utilise le constructeur (par exemple une méthode de la classe)

Item 48 :

Il faut éviter les `float` et les `double` si on a besoin de précision (comme pour des calculs monétaires) car ils ne sont pas assez précis (arrondis). Il faut utiliser `BigDecimal`, `int` ou `double` selon les cas.

Item 49 :

Il est préférable d'utiliser un type primitif par rapport à sa version "boxed" (par exemple `int` vs `Integer`). C'est plus simple, plus rapide et moins propice à avoir des bugs cachés (notamment des problèmes de performances liés à des unboxing cachés ou des problèmes de comparaison erronnées à cause de `==`)


Misc :

Possibilité d'avoir des blocs de code qui s'exécutent soit au chargement de la classe, soit à son instantiation avec, respectivement, le static initializer blocl et l'instance initializer block https://www.baeldung.com/java-static-instance-initializer-blocks (un peu en mode "ngInit" d'Angular sans avoir à passer dans le constructeur, ce qui peut être utile en cas de multiples constructeurs ou de constructeur privé)

On peut créer des Map avec des enumérations comme clé : EnumMap https://docs.oracle.com/javase/8/docs/api/java/util/EnumMap.html
