# Basic Flask
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/bmoh1/Basic-Flask/HEAD?labpath=main.py)

This is a simple project which aims to uses Flask to build an internal web framework. The main Idea is to build an internal HTML webpage which accepts tasks from Clients. Flask API is built to receive these orders and send them to backend database Flask-SQLAlchemy (Webpage -> Flask -> SQLAlchemy DB)

Inspiration was taken from https://github.com/jakerieger/FlaskIntroduction but I have made some enhancements such as code enhancements and HTML CSS edits. For example, ```db.create_all()``` raises and error ```RuntimeError: Working outside of application context``` if there is no app context because all access to ```db.session``` needs an active Flask application context.

Website acts like a Task master to keep a record of tasks/orders each time a user visits the website. There is a few functionalities:
1. Add a new task
2. Update a new task
3. Delete a new task

# Contents of Project
1. main.py - This runs Flask Web Application
2. Templates
    - ```base.html``` - sub-boiler HTML template used for HTML web templates (Run ```html 5``` in VSC for premade template)
    - ```index.html``` - builds upon ```base.html```
    - ```update.html``` - this is for updating the webpage based on update button
3. Static\Css\main.css
    - For setting up CSS Styling
4. .venv
    - For setting up your own virtual environment - please do not use this but create your own via ```python -m venv <name of venv>``` in Git Bash
5. instance/Database.db
- SQLAlchemy database as an extension of Flask app to store user inputs from internal HTML website
6. Readme.md
- For user guide and overview of what this project is
7. Requirements.txt
- For installing all packages needed for this project

# Installation
 To use this project:
1. Download the GIT repository via URL provided on GitHub Repo - ```Git Clone <Repo URL>``` on Git Bash)
2. Please set up your own Python virtual environment using Git Bash command ```python -m venv <name of virtual env>```
3. Download all required packages based on the file 'requirements.txt' on Git Bash using the command ```pip install -r requirements.txt```

# Important notes
1. Download Flask Application and configure ```Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy Unrestricted``` in powershell to allow Flask Application to run
2. Folder Templates:
- ```base.html``` is where we create HTML5 boiler plate 
    - ```{% block head %}{% endblock %}``` and ```{% block head %}{% endblock %}``` is for overriding specific parts of base HTML template for head and body tags 
- ```index.html``` inherits web template from ```base.html```
3. Static
- ```Static/css/main.css``` is for CSS Styling of html webpage
4. instance/Database.db
- This is created using Flask SQLALCHEMY but to initialise an instance of it, you need to run Python shell and enter the following commands:
```
>>> from project import app, db
>>> app.app_context().push()
>>> db.create_all()
```

# Future enhancements
Future enhancements can include having this deployed to cloud platform services such as Heroku to mimick actual deployment of websites. 
