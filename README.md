# Simple-Django-Newsletter-Web-App
Simple Django Newsletter Web App  
This will be a 2 part project;   

Part 1:  

1. Setup a virtual environment  
2. Install Django and other dependancies to launch on Heroku 
3. Create multiple pages, ie... Home page, About page, Sign up page 
4. Use Django Templates and Template Tags 
5. Bootstrap the app
6. Launch on Heroku  

Part 2:  

1. Create the backend, admin section 
2. Create a models.py 
3. Create a sign-up form

This is the sample website that we are building:
https://landingpage001.herokuapp.com/



#########################################################################################################################

Django Project Notes


Create a simple Django Newsletter web app:
Home page, About page, Sign up page
launch it live on Heroku 




1.0	create directory for project

	mkdir project1



1.1	set up virtual environment

	virtualenv -p python3 .
	
	activate environment

	source bin/activate



1.2	create a directory to store code
	
	mkdir src 

	open up VScode in this directory

####### run VS Code Text Editor #######

	code .

	cd into src
	


2.0	install dependancies to launch on heroku 

	pip freeze

	pip install django==(any or latest version)

	pip install django

	pip install dj-database-url 
	
	pip install psycopg2

	pip install pillow

	pip install gunicorn




2.1	create a django project

	django-admin startproject (name_of_project) .



2.2	test server

	python manage.py runserver



2.3	sync database

	python manage.py makemigrations

	python manage.py migrate



2.4	add a requirements.txt

	pip freeze > requirements.txt



2.5	create a superuser

	python manage.py createsuperuser
	
	create password:

	-----  landingpage2019  -----



2.6	create an django app

	python manage.py startapp pages (name of app)



2.7	go to settings file and add the new app 



3.0	create a templates directory in the root (src)

	home.html
	about.html
	signup.html
	base.html
	navbar.html


3.1	need to add templates directory into settings files under TEMPLATES = []

	os.path.join(BASE_DIR, "templates")



3.2	create a homepage, about, contact

	go into pages directory 
	
	open up views.py


	from django.http import HttpResponse
	from django.shortcuts import render	

	def home_view(request, *args, **kwargs):
    		return render(request, "home.html", {})

	def about_view(request, *args, **kwargs):
    		return render(request, "about.html", {})

	def signup_view(request, *args, **kwargs):
    		return render(request, "signup.html", {})


3.3	route the pages in urls.py



4.0	Django Templates Tags

	{% block content %}

	{% endblock %}

	{% extends 'base.html' %}

	{% include 'navbar.html' %}



5.0	cdn bootstrap 4.0

	bootstrap css:
	
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">

	bootstrap js:
	
	<script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>



########## launch web app online Heroku ########## 



6.0	initialize git 

	git init

	git status

	git add --all

	git commit -m "Initial commit"



6.1 	create .gitignore file

	copy and paste this file to ignore some python files
	
	https://raw.githubusercontent.com/github/gitignore/master/Python.gitignore



6.3	create a Procfile in the src directory

	web: gunicorn landingpage.wsgi --log-file -


	install heroku cli

	brew install heroku

	update heroku 

	npm install -g heroku 

	check version 

	heroku --version

	heroku login

	heroku create landingpage001(name of web app)

	add the new heroku url to settings ALLOWED_HOSTS
	
	DEBUG = False

	test heroku local server

	git status

	git add .

	git commit -m "updated setting files"

	heroku local web

	heroku open



6.4	git push heroku master


	
6.5	in case we get an error

	disable collect static

	heroku config:set DISABLE_COLLECTSTATIC=1

	git push heroku master





AND YOU WE ARE LIVE HOUSTON!










