# Kubernetes introduction

So the whole point about kubernetes is to follow a declarative paradigm on how
the network architecture ofa system should look like, and have kubernetes
manage how it should set that up. What does this mean?

- Instead of telling how kubernetes should set up the system, we declare how we
  want the system to look like, and let kubernetes handle the implementation

Kubernetes is also referred to as k8s for short, which is what we will be using
from now on to refer to it.

## K8s origins

k8s is a software system originated from google and is written on
Golang. It is a container orchestration system which handles multihost
deployments of containers.

It takes docker images and deployment manifests, and
does its best at orchestrating the desired system based on the deployment
manifests. This lets us write in an declarative style, which has the advantages
of being clearer in defining our system, and abstracts away implementation
details.

## K8s system overview

k8s is based on masters and nodes (aka minions or workers). The masters and
nodes may be deployed on VMs, containers, physical machines, or whatever runs
a linux system underneath.

Furthermore the k8s system can be split into pods, services and deployments.
These will have their own subfolder and chapter in the repository, so we are
not getting into them here.

### K8s Masters

Masters run essentially 4 systems:
- API server
    * Master front-end
    * The component that `$kubectl` (k8s client) talks to
- Cluster store
    * Holds the system configuration
- Controllers
    * Monitors the k8s system for changes and runs the appropriate commands
- Scheduler
    * Watches the api-server and assigns work to nodes

### K8s nodes

Simple workers, theu run essentially 3 systems:

- Kubelet
    * k8s agent, interacts and takes commands from master
    * Exposes endpoint :10255 with paths:`/spec` `/healthz` `/pods`
- Container runtime
    * pulls images, starts and stops containers
    * Docker or rkt
- Proxy
    * Handles node networking
    * Each pod gets its own ip, but containers the pod share the IP of the pod



