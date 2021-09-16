## Services

## Mutli-Instance Application, challenges

1. How to distribute all incoming requests to all the instances.
2. How to detect if an instance is either available or unavailable
3. How to update the instances
	3.1 Start sending request to newer instance
	3.2 Stop sending request to older instance (terminating)


## The above challenges are RESOLVED by "Services" in Kubernetes

1. Each service is MAPPED to Set of Pods by using "label selector"
2. Each Service has collection of Endpoints (each endpoint actually represents
		POD IP and PORT)
3. A Special "Endpoint-Controller" would simply update the "Available" and "Unvailable Endpoint"
4. Endpoint-Controller can even detect the changes in pod-count.

```bash
kubectl apply -f demo7.yaml
kubectl get svc app1-svc
kubectl describe ep app1-svc
curl localhost:8080
curl localhost:8080
curl localhost:8080
```

