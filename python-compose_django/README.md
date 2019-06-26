Using Docker Compose to set up and run a Django/PostgreSQL app. 

start with:
`docker-compose up`


db config -> composeexample/settings.py
```PYTHON
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'postgres',
        'USER': 'postgres',
        'HOST': 'db',
        'PORT': 5432,
    }
}
```


[Link](https://docs.docker.com/compose/django/)