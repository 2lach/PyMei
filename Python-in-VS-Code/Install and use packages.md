# install and use packages

from [install-and-use-packages](https://code.visualstudio.com/docs/python/python-tutorial#_install-and-use-packages)

setup python linter (user)     
`$ /usr/local/bin/python3 -m pip install -U pylint --user`

connect to project         
`$ /usr/local/bin/python3 /Users/z/Desktop/Code/PythonFlask/Python-in-VS-Code/hello.py`

setup project virtual enviroment     
`$ python3 -m venv env`

install matplotlib     
`$ python3 -m pip install matplotlib`

activate (virtual) env     
`$ source env/bin/activate`
 create env and launch debugger

Start the project with python:   
from terminal:   
`$ python3 standardplot.py`  

run from file (right-click -> run Python file in terminal)
`$ /usr/local/bin/python3 /Users/z/Desktop/Code/PythonFlask/Python-in-VS-Code/standardplot.py`

run with debugger   
`$ cd /Users/z/Desktop/Code/PythonFlask ; env PYTHONIOENCODING=UTF-8 PYTHONUNBUFFERED=1 /usr/local/bin/python3 /Users/z/.vscode/extensions/ms-python.python-2019.5.18875/pythonFiles/ptvsd_launcher.py --default --client --host localhost --port 49631 /Users/z/Desktop/Code/PythonFlask/Python-in-VS-Code/standardplot.py`

 exit virtual env     
`$ deactivate`
