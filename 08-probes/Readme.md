## Health Probes

> Just becouse a container status is RUNNING doesn't mean
  your application inside container is running as well!


> User requests http://servicename/api/find response received is HTTP/500

> For End User / Client is application is returning 404/500
  that means it's not running properly.


When application returns 400/500 (Server errors) I want instance to be marked
  as UNHEALTHY and should not receive any more requests
	READINESSPROBE 


When application returns 400/500 (Server errors) I want instance to be marked
  as UNHEALTHY and it should be RESTARTED.
	LIVENESSPROBE

Delay the execution of LIVENESS & READINESS probes untill application is READY
	STARTUPPROBE

Probes could be either
	HTTP probe:  => http://POD-IP:CONTAINER-PORT/PATH
			https://POD-IP:CONTAINER-PORT/PATH

	TCP probe:  => tcp://POD-IP:CONTAINER-PORT

	Exec Probe: => Launch a process or command and expect it return ZERO


## Demo

```bash
$ kubectl apply -f deploy.yml
$ kubectl get po
$ kubectl describe ep probe-demo-svc
```

```bash
$ kubectl get po -l app=demo1
## Copy the name of first pod
$ kubectl exec -it PODNAME -c web -- sh
$ cd /usr/share/nginx/html
$ mv index.html index.html.txt
$ exit
# Wait for 20 seconds
$ kubectl get po -l app=demo1
```
