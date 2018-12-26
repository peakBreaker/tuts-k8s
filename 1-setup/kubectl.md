## kubectl

Kubectl is the k8s client for CLI.  Its really handy and used all over the
place for controlling a kubernetes cluster.

### Getting started

The install of kubectl may depend on your OS.  For Arch linux its the followin:

```
$ yay -S kubectl
```

That should cover it


### Running kubectl

Kubectl is a kubernetes client for connecting to and controlling a kubernetes
cluster

- Viewing cluster info:

```
$ kubectl config current-context
$ kubectl get {nodes,pods,rc,service,deployment}
$ kubectl describe
```

- Applying new config to cluster:

```
$ kubectl create -f <file.yml>
$ kubectl apply -f <file.yml> # on changes to cluster
```

There will be more commands in the specific tutorials on pods, services,
deployemnts etc.
