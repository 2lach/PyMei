# how to setup an flask app

`$ mkdir PythonFlask` 

`$ cd $_`



init venv, (comes with py3) this creates venv dir    
` $ python3 -m venv venv`

```
'venv'--| 
        |- bin/        
        |- include/    
        |- lib/        
        |- pyvenv.cfg
```        

 activate venv   
` $ ($ProjectRoot) . venv/bin/activate`    

install Flask    
` $ pip install Flask`    

create main file    
` $ v hello.py`

```PY
# Import the Flask class.
from flask import Flask

# Create an instance of this class
app = Flask(__name__)

#use the route() decorator to tell Flask what URL should trigger our function
@app.route('/')
def hello_world():
    return 'Hello, World!'
```

export the FLASK_APP environment variable    
` $ export FLASK_APP=hello.py`    

run app with:    
` $ flask run`    
or   
` $ python -m flask run`    
(will run on http://127.0.0.1:5000/)    

to exit venv   
` $ deactivate`   
