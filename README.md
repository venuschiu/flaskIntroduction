# Flask CRUD Web Application

This project is a task management web application that allows the users to add, read, update & delete tasks. 

[Live Demo](https://vvflaskcrudapptutorial.herokuapp.com/)

# Technology Used
Python 3.9.7


Package
Flask
SQL Lite 
SQLAlchemy


# Set up packages 

Installing virtual environment

virtualenv is a tool to create isolated Python environments
`pip3 install virtualenv`


Setting up virtual environment for the project
`virtualenv env`

# Database
SQLlite is used.
create the database and tables
```
from server import db
db.create_all()
```

# Data Models

There's only one table to store the tasks and it is defined by Python class

Column | Type 
---------|----------
 id | Integer 
 content | String(200) 
 completed | Integer
 |date_created | Date Time

```
class Todo(db.Model):
    id = db.Column(db.Integer, primary_key = True)
    content = db.Column(db.String(200) , nullable = False)
    completed = db.Column(db.Integer, default = 0)
    date_created = db.Column(db.DateTime, default=datetime.utcnow )

    ## string representation of the class' object
    def __repr__(self):
        return '<Task %r>' % self.id
```



# Routes

# Templates
## base.html
This is the base html template that all other pages would be based on. It only has header and body and it is referring to the static\main.css class. Here jinja2 syntax is used. 

```
....
    <link rel = "stylesheet", href = "{{url_for('static', filename = 'css/main.css')}}">
    {% block head %} {% endblock %}
</head>
<body>
    {% block body %} {% endblock %}

</body>
</html>
```

# CSS

web apps hosted on heroku





# Reference

<https://youtu.be/Z1RJmh_OqeA>

using visual code studio

use gunicorn as the web server
pip3 freeze > requirement.txt, which produces a files with all dependencies

use jinja syntax



