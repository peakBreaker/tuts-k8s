## Minikube

Minikube is a real great tool for getting started with kubernetes on your own
machine. 

### Getting started

Depending on your OS and devenv, installing it can be different.

Since I am running Arch, I install from AUR with the following:

```
$ yay -S  minikube
```

Minikube also needs virtualization to be enabled for the OS on the machine. It
also needs virtualbox installed (or xhyve or similar)

With Arch we then install the following packages:

```
$ sudo pacman -S virtualbox-host-modules-arch
$ sudo pacman -S virtualbox
$ sudo pacman -S +,linux-headers,,,,
```

Again, this is Arch specifica and may change. Look up the instructions by
duckduckgo-ing  the instructions for your OS.

### Running minikube

It should be as simple as running `$ minikube start`. This will set up a local
kubernetes cluster with master and a single node, so that we can test it out.
It also configures `kubectl` to run with minikube context.

Some other handy minikube commands are the following:

```
$ minikube ip
$ minikube dashboard
$ minikube stop
$ minikube delete
```
