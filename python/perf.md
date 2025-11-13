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

