# flask-example-app
Example repository for deploying a Flask app on a container using Gunicorn as a WSGI server.
#

## Requirements:
- [Docker](https://docs.docker.com/get-docker/)
- [docker-compose](https://docs.docker.com/compose/install/) (optional)

## How to try it:
Build and run using the following commands:

```
$ docker build . -t flask-docker-example:latest
$ docker run --name example -p 5000:5000 --rm -it flask-docker-example:latest
```

You can also run it using `docker-compose`:

```
$ docker-compose up
```

The endpoint should then be accessible on http://localhost:5000.

```
$ curl http://localhost:5000 
> Hello World!%
```
