# flask-example-app

Example repository for deploying a Flask app on a container using Gunicorn as a WSGI server.

Build and run with the following commands:

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