# Deployment

A Recommended object for deploying containerized workload.
Contains "ReplicaSet" and "RevisionHistory"
Provides Update strategies: Recreate & RollingUpdate

## Recreate

1. Simple and Easier, Delete old pods and then deploy new ones
2. Light on system resources
3. Results in downtime, due to pods not available while deployment

## RollingUpdate

1. Deploying few instances at once and replacing them with newer instances
2. Newer instance might be deployed before old one completely terminates.
3. Spike in resource utilization due to new pods deployed before older gets deleted.
4. Negligible or no downtime.

## Demo
```
$ kubectl apply -f demo6.yaml
$ kubectl get rs -o wide
$ kubectl set image deploy/app1 web=mahendrshinde/myweb:2 --record
$ kubectl get rs -o wide -w
CTRL+C
$ kubectl set image deploy/app1 web=mahendrshinde/myweb:3 --record
$ kubectl rollout history deploy/app1
$ kubectl rollout undo deploy/app1
$ kubectl get rs -o wide -w
CTRL+C
$ kubectl delete -f demo6.yaml
```