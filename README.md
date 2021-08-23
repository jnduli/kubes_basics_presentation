# Static File
Running from docker

```
cd static_content
docker build -t static:0.1.0 -f Dockerfile_static_content .
docker container run --publish 8000:80 --name static_example static:0.1.0
# get ip with this
docker container inspect static_example | grep "IPAddress"
curl ip_address_got_from_above
```

Running within kubes:

Loadbalancer can expose deployment, pods, etc.

should explain concept of pod, loadbalancer

```
minikube start
eval $(minikube -p minikube docker-env)
docker build -t static:0.1.0 -f Dockerfile_static_content .
kubectl apply -f k8s/deployment.yml
kubectl get services
kubectl get pods
kubectl get services # notice ip address of service
curl $(minikube ip):ip_from_above
```

# Kubernetes Node JS project

```
cd vue_project
docker build -t vue:0.1.0 -f Dockerfile .
docker container run --publish 8080:8080 --name vue_example vue:0.1.0
```

With ingress controller

```
minikube start
eval $(minikube -p minikube docker-env)
docker build -t vue:0.1.0 -f Dockerfile .
minikube addons enable ingress
kubectl apply -f k8s/
kubectl get ingress
kubectl get services
```


# Kubernetes Comic Server
Service with database and django thing.

