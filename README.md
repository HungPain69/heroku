# heroku
Getting started deploy django project on heroku

$ cd ~/Desktop
$ mkdir hung
$ cd hung
$ pipenv install django
$ pipenv shell
(hung) $ django-admin startproject project .
(hung) $ python manage.py startapp app

# setting.py
  INSTALLED_APPS = [
  ...
  'pages.apps.PagesConfig', 
  ...
  ]
  
  ALLOWED_HOSTS = ['*']
  
  TIME_ZONE = 'Asia/Ho_Chi_Minh'
  


(hung) $ heroku login

#Pipfile
  [requires]
  python_version = "3.7"
  
(hung) $ pipenv lock
(hung) $ touch Procfile

#Procfile
  web: gunicorn project.wsgi --log-file -   #project is my project name

(hung) $ pipenv install gunicorn


(hung) $ git init
(hung) $ git status
(hung) $ git add -A
(hung) $ git commit -m 'commit'

#push your code project on github

(hung) $ heroku create pain69
(hung) $ heroku git:remote -a pain69
(hung) $ heroku config:set DISABLE_COLLECTSTATIC=1
(hung) $ git push heroku master
(hung) $ heroku ps:scale web=1
(hung) $ heroku open

