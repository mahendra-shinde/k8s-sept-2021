# Namespaces

Kubernetes API Object "namespace" is just a logical container for all other kubernetes objects (like pods, configmaps, deployments etc.).

## To create namespaces defines in demo1.yaml file:

```bash
$ kubectl apply -f demo1.yaml
$ kubectl get ns 
```

## To delete all namespaces 

```bash
$ kubectl delete -f demo1.yaml
```