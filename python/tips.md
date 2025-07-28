

Pour voir la stack complète d’une exception en point d’arrêt si elle n’est pas présente : 

```
try:
  raise NotImplementedError("No error")
except Exception as e:
  exc_type, exc_obj, exc_tb = sys.exc_info()
  fname = os.path.split(exc_tb.tb_frame.[f_code.co](http://f_code.co/)_filename)[1]
  print(exc_type, fname, exc_tb.tb_lineno)
```


Dans Pytest, rajouter -s pour voir les “print”
