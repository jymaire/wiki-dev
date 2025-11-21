# Instru

https://medium.com/naukri-engineering/lets-profile-your-flask-app-70e25d149738

CPU :

from werkzeug.middleware.profiler import ProfilerMiddleware

@profile sur la fonction à suivre (pas l'impression que ce soit nécessaire)


app = Flask(__name__)
app.config['PROFILE'] = True
app.wsgi_app = ProfilerMiddleware(app.wsgi_app)

Visu :

snakeviz profiler_data_file.prof


# Tips

On peut utiliser slots pour optimiser la mémoire https://www.pythonmorsels.com/__slots__/

Explication :

>By default, Python classes store instance attributes in a dynamic dictionary (__dict__), which offers flexibility but comes with memory overhead and slightly slower attribute access.
>
>Using __slots__ allows you to explicitly declare a fixed set of attributes for a class. This eliminates the need for a __dict__, reducing memory usage – which is especially beneficial when creating many instances of a class. It also leads to marginally faster attribute access due to the simplified internal structure.
>
>While __slots__ does restrict dynamic attribute assignment, this trade-off is often worthwhile in memory-constrained environments or performance-sensitive applications. For lightweight classes or data containers, applying __slots__ is a simple way to make your code more efficient.

source : https://blog.jetbrains.com/pycharm/2025/11/10-smart-performance-hacks-for-faster-python-code/

