source : https://www.youtube.com/watch?v=hSfylUXhpkA

(9:24)

Comparator :

    Avant : 

    Collections.sort(words, new Comparator<String>() {
        public int compare(String s1, String s2){
            return Integer.compare(s1.length(), s2.length());
        }});

    Maintenant :
    Collections.sort(words,
    (s1,s2) ->Integer.compare(s1.length(), s2.length));

    Maintenant mais mieux :
    Collections.sort(words,comparingInt(String:length));

    Encore mieux (sur une List) : 
    words.sort(comparingInt(String:length));

    La nouvelle syntaxe fonctionne sur de l'inférence de type.




Raw types

    A raw type is a name for a generic interface or class without its type argument:

    List list = new ArrayList(); // raw type

    Instead of:

    List<Integer> listIntgrs = new ArrayList<>(); // parameterized type

    => Ne PAS utiliser de raw types

    source du texte : https://www.baeldung.com/raw-types-java


Functionnal interfaces

    A functional interface is an interface that contains only one abstract method. A functional interface can have any number of default methods. Runnable, ActionListener, and Comparable are some of the examples of functional interfaces. 

    source du texte : https://www.geeksforgeeks.org/functional-interfaces-java/


