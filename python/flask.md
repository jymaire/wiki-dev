# Tips

## Trouver une classe à partir d'un call HTTP

avec `app.url_map` on peut trouver le endpoint associé à un appel HTTP. Puis à partir de ce nom de endpoint et `napp.view_functions.get('endpoint_name')` cela va donner le nom de la classe
