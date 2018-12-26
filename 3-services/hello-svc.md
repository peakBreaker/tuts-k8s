## Kubernetes Services

Services are the machines in the cluster which handles the networking
functionality.

Till now we have deployed pods, but we cant access them. Due to the nature of
pods, we shouldn't attempt to access pods directly either - they have an IP,
but they are treated as kattle and will run and die, so we cant rely on the pod
IP.  This is where the service comes in.

Services have an ip, port and DNS we can rely on, and they let us easily
connect to our pods.

### Getting started

Make sure kubernetes and kubectl is set up

#### The iterative way

We can set up and expose our pods with a service in a direct and iterative way.
This is handy to know about, but using the declarative method below should be
preferred over this way:

```
$ kubectl expose rc <ReplicationController> --name=servicename
--target-port=<pod-port> --type=NodePort
```

This presumes that there is a replicationcontroller running already which runs
some pods.

Use `$ minikube ip` to get the ip if using minikube, otherwise it should be the
public ip of your server and use the nodeport in `$ kubectl describe
service` to access the exposed service

#### The decalrative way

In this folder there is a svc.yml file which declares a service.  This service
will connect to all pods with the `app: hello-world` label, defined in the
selector.  Look at the yml file for details on the service - it should be quite
straight forward.
