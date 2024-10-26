# Este proyecto esta que se esta realizando es mediante el tutorial del propio Django

# Entorno vitual

 - Creacion del entorno virtual

 ```
 py -m venv venv  
 ```


 - Activacion 

 ```
 .\venv\Scripts\activate
 ```

# Instalacion de Django y como mandos de uso

- Instalacion 
```
pip install django
```

- Verificacion de version

```
py -m django --version
```

- Creacion de proyecto

```
django-admin startproject mysite
```

- Activacion del servidor local

```
py manage.py runserver
```

# Migracion

```
py manage.py migrate
```

# Crear modelos 

En el archivo models.py creamos los modeles para la base de datos

```
from django.db import models


class Question(models.Model):
    question_text = models.CharField(max_length=200)
    pub_date = models.DateTimeField("date published")


class Choice(models.Model):
    question = models.ForeignKey(Question, on_delete=models.CASCADE)
    choice_text = models.CharField(max_length=200)
    votes = models.IntegerField(default=0)
```

# Activar los modelos

```
INSTALLED_APPS = [
    "polls.apps.PollsConfig",
    "django.contrib.admin",
    "django.contrib.auth",
    "django.contrib.contenttypes",
    "django.contrib.sessions",
    "django.contrib.messages",
    "django.contrib.staticfiles",
]
```

Para incluirlo en path 

```
py manage.py makemigrations polls
```

