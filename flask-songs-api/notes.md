## Flask for node developers

This is a a basic CRUD server-side application using Python and Flask, geared toward JavaScript developers versed in Node and Express. Similar to Express, Flask is a simple, yet powerful micro-framework for Python, perfect for RESTful APIs.

objectives:
Set up a Python development environment
Create and activate a virtual environment
Using SQLite, apply a schema to the database and interact with the database using the basic CRUD functions
Build a CRUD app using Python and Flask


setup a virtual enviroment
`python3 -m venv env`

activate the virtual env 
`<source> . env/bin/activate`  
if it worked (env) should show in your prompt

install flask
`pip install Flask==0.12.1`

create requirements.txt file 
`pip freeze > requirements.txt`

Add a main app file
this will handle routing and run our application 
`touch app.py`

setup a file to setup our database schema:
`touch models.py`


### Database Setup
setup of a SQLite3 since it’s part of the Python standard library, requires little (if any) configuration, and is powerful enough for small to mid-size applications (e.g., the majority of web apps).
`touch songs.db`

then start a new SQLite session:
`sqlite3 songs.db`

Then run:  
`sqlite> .databases`

Create a schema in models.py:
```PYTHON
import sqlite3

def drop_table():
    with sqlite3.connect('songs.db') as connection:
        c = connection.cursor()
        c.execute("""DROP TABLE IF EXISTS songs;""")
    return True


def create_db():
    with sqlite3.connect('songs.db') as connection:
        c = connection.cursor()
        table = """CREATE TABLE songs(
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            artist TEXT NOT NULL,
            title TEXT NOT NULL,
            rating INTEGER NOT NULL
        );
        """
        c.execute(table)
    return True


if __name__ == '__main__':
    drop_table()
    create_db()

```

In the terminal, exit SQLite
`sqlite> .exit`

Run the script to create our table:
`python models.py`

```SHELL
sqlite3 songs.db

sqlite> .table
songs

sqlite> .schema
CREATE TABLE songs(
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            artist TEXT NOT NULL,
            title TEXT NOT NULL,
            rating INTEGER NOT NULL
        );

sqlite> .exit
```
We won’t be do a database migrations but to change schema check out [Flask-Migrate](https://flask-migrate.readthedocs.io/en/latest/)


### Routes
Let’s start with an overview of the routes, following RESTful principles:

```TABLE

Endpoint    	        Result  	            CRUD    	HTTP
/api/songs	            Returns all songs	    Read	    GET
/api/song/<song_id>     Returns a single song	Read	    GET
/api/songs	            Adds a single song	    Create	    POST
/api/song/<song_id>	    Updates a single song	Update	    PUT
/api/song/<song_id>	    Deletes a single song	Delete	    DELETE

```

### currently at -> https://mherman.org/blog/flask-for-node-developers/#post
