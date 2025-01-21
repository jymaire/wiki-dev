Item 1 :

Si on créé une classe immuable (cf item 15) alors utiliser `equals` ou `==` est équivalent sémantiquement. Mais utiliser `==` est meilleur en terme de performances. 
(raison de la règle Sonar sur les énumerations https://github.com/SonarSource/sonar-java/blob/master/java-checks/src/main/java/org/sonar/java/checks/EnumEqualCheck.java )

Item 2 :

Dans les constructeurs privés, on peut lancer une https://docs.oracle.com/javase/8/docs/api///?java/lang/AssertionError.html pour s'assurer que personne n'utilise le constructeur (par exemple une méthode de la classe)

Misc :

Possibilité d'avoir des blocs de code qui s'exécutent soit au chargement de la classe, soit à son instantiation avec, respectivement, le static initializer blocl et l'instance initializer block https://www.baeldung.com/java-static-instance-initializer-blocks (un peu en mode "ngInit" d'Angular sans avoir à passer dans le constructeur, ce qui peut être utile en cas de multiples constructeurs ou de constructeur privé)
