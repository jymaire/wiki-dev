Ajouter des tests hauts niveaux pour éviter les régressions

Ajouter des guards clause en début de fonction pour sortir au plus tôt

Réduire les niveaux d'indendations 

On peut grouper des conditions de if dans des lambas https://youtu.be/mH7e7fs9gaE?t=1109 :

```
list_conditions = [
lambda: is age > 42,
lamba: not user.allowed,
}
if any( rule() for rule in list_conitions):
  print('wrong')

```
https://www.youtube.com/watch?v=mH7e7fs9gaE
