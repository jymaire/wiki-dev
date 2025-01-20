Item 1 :

Si on créé une classe immuable (cf item 15) alors utiliser `equals` ou `==` est équivalent sémantiquement. Mais utiliser `==` est meilleur en terme de performances. 
(raison de la règle Sonar sur les énumerations https://github.com/SonarSource/sonar-java/blob/master/java-checks/src/main/java/org/sonar/java/checks/EnumEqualCheck.java )
