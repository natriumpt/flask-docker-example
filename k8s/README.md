# flask-example-app
Example repository for deploying the previously created image on a Kubernetes cluster.
#

## Requirements:
- [Docker](https://docs.docker.com/get-docker/)
- [minikube](https://minikube.sigs.k8s.io/docs/start/)

## How to try it:

From this directory, run the following command to automatically create a deployment and a corresponding load balancer.

```
kubectl create -f flask-docker-example-deployment.yml -f flask-docker-example-service.yml
```

The following commands can also be used, however, bear in mind that the container port will not be able to be set via the `create deployment` command, and as such, will use the default image port (in this case 5000)/

```
kubectl create deployment flask-docker-example --image=natriumpt/flask-docker-example
kubectl expose deployment flask-docker-example --type=LoadBalancer --name=flask-docker-example --port=5000
```

The deployment can also be scaled with the following command:
```
kubectl scale deployment flask-docker-example-deployment --replicas=4
```

Confirm the pods are available using:

```
kubectl get pods
```

The endpoint should then be accessible on http://localhost:5000.

```
$ curl http://localhost:5000 
> Hello World!%
```

Finally, clean up by running the following commands:
```
kubectl delete deployment flask-docker-example-deployment
kubectl delete service flask-docker-example-service
```