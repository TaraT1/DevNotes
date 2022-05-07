---
id: n7x24srdf04dykyp5y7k4l1
title: Heroku
desc: ''
updated: 1651599445671
created: 1651599334479
---
Notes for Obsidian
## Configure App for Heroku
- Create and update requirements.txt (for dependendencies)
    ```pip freeze > requirements.txt```
    - takes snapshot of versions of packages in virtual env
- set up environment variables in config vars and setup.sh. ***Note: will implement from config vars. Eliminate ' '
- run app using Procfile, gunicorn
    ```pip install gunicorn```
    ```touch Procfile``` creates file
        ```web: gunicorn app:all``` (App should be in app.py)
        
  ??? should Heroku specific files be separated?
  ??? GUI

### For Database, Use Migrations
    ```
    pip install flask_script
    pip install flask_migrate
    pip install psycopg2-binary
    ```

    In manage.py
    ```
    from flask_script import Manager
    from flask_migrate import Migrate, MigrateCommand

    from app import app
    from models import db

    migrate = Migrate(app, db)
    manager = Manager(app)

    manager.add_command('db', MigrateCommand)


    if __name__ == '__main__':
        manager.run()
    ```

    Run local migrations using manage.py
    ```
    python manage.py db init
    python manage.py db migrate
    python manage.py db upgrade
    python manage.py db stamp head - makes current same

    ```
    For example project file structure is:
    >__pycache__
    >migrations
    .gitignore
    app.py
    manage.py
    models.py
    Procfile
    requirements.txt
    setup.sh

## Deploy to Heroku
- Create Heroku app
``` heroku create app_name ```
    - copy git url
    - Heroku dashboard will have app_name
- Add git remote for Heroku to local repo using git url
```git remote add heroku heroku_git_url ```
 
## Add postgresql add on for db
- create db and connect to app
```
heroku addons:create heroku-postgresql:hobby-dev --app 
name_of_application
```
- hobby-dev refers to free version of addon tier

Run
```
heroku config --app
name_of_application
```

Fix configurations in Heroku dashboard
-settings\config vars: add required env vars

```git push heroku main```

## Run migrations once app is deployed
```heroku run python manage.py db upgrade --app name_of_application

- Open app from Heroku Dashboard. 
- Make additional requests using curl or Postman as build app and make more complex endpoints

 References:
    [Deployment Docs](https://devcenter.heroku.com/categories/deployment)
    [Getting Started with Python](https://devcenter.heroku.com/articles/getting-started-with-python)
   

## Useful Heroku CLI Commands
- heroku login
## Github
- heroku deploys from main branch
- git push heroku main
- [Setup heroku staging environment](https://devcenter.heroku.com/articles/multiple-environments)





