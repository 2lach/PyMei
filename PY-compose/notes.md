DOCKERFILE

Build an image starting with the Python 3.7 image.
`FROM python:3.7-alpine`

Set the working directory to /code.
`WORKDIR /code`

Set environment variables used by the flask command.
`ENV FLASK_APP app.py`
`ENV FLASK_RUN_HOST 0.0.0.0`

Install gcc so Python packages such as MarkupSafe and SQLAlchemy can compile speedups.
`RUN apk add --no-cache gcc musl-dev linux-headers`


Copy requirements.txt and install the Python dependencies.
`COPY requirements.txt requirements.txt`
`RUN pip install -r requirements.txt`


Copy the current directory . in the project to the workdir . in the image.
`COPY . .`

Set the default command for the container to flask run.
`CMD ["flask", "run"]`


By adding:
```docker
    volumes:
      - .:/code
```
See -> docker-compose-dev.yml

it enables changes in codebase with reload


`docker-compose ps` = what is currently running (cleaner version of docker ps)

`docker-compose run web env` =  See what environment variables are available to the web service

stop but save data:
`docker-compose stop`

teardown kill all data:
`docker-compose down --volumes`
By passing `--volumes` removes the data volume used by the Redis container