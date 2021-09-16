# ReplicaSet

Collection of Pods with Scalability and Self Healing.
Pods controlled by ReplicaSet, would self heal on delete. (replaced with newer clone)
Every time a new pod is created, its name and ip would be different.
Onces 'scaled out' (up) a new pod would be added.
Onces 'scaled in' (down) an existing pod would be deleted (cannot predict which one !!)

## How to scale out (increase replicas) or scale in (decrease replicas)

```bash
$ kubectl scale rs <REPLICASETNAME> --replicas=<NUMBER>
```

## Demo

```bash
$ kubectl apply -f demo5.yaml
$ kubectl get po
$ kubectl get rs
$ kubectl delete po -l app=app1
$ kubectl get po
$ kubectl delete -f demo5.yaml
```


