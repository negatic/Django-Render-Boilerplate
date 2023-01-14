# Django Render Boilerplate
This is a boilerplate project to quickly build and deploy django projects on Render cloud services
Note: the DEBUG setting will be automatically set depending on the place you're running/deploying your project so you don't have to pass any environment variable for it.
### Database
By default this project uses sqlite in development environment (DEBUG=True) and Postgres in production settings (DEBUG=False)
You have to pass your PG database connection string to the 'DB_STRING' environment variable
### Static Files
Static files are served using whitenoise, your development/production environment will be automatically recognized and served accordingly so you don't need to change any settings when on localhost
### SecretKey
Make sure to pass your secretkey to ```'SECRET_KEY'``` environment variable in production
### SuperUser
A new superuser will be created when you first deploy your project, 

```
DJANGO_SUPERUSER_USERNAME=your_username
DJANGO_SUPERUSER_PASSWORD=your_password 
DJANGO_SUPERUSER_EMAIL="admin@admin.com"
```
Note: Make sure to comment the createsuperuser line in build.ssh after your first deploy, otherwise your future deployments will get failed
### Python Version
You can pass your desired python version with this environment variable:
```PYTHON_VERSION=3.11.1```

### WEB CONCURRENCY
The number of worker processes for handling requests. Default is 1.
```WEB_CONCURRENCY=4```

### pyproject.toml
This file contains name,description and your project dependencies, make sure you update it according to your needs

