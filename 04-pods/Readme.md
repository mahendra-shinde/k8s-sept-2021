# Pods

Pods are atomic units, contains one or more containers and are deployed on "worker" nodes.

## Deploying a pod with configmap (ConfigMap is Optional)

```bash
$ kubectl apply -f demo4.yaml
$ kubectl get po -n dev-ns
$ kubectl describe pod mypod -n dev-ns
$ kubectl exec -n dev-ns -it mypod -c c1 -- sh
$ echo " $DBUSER / $DBPASS"
$ exit
```