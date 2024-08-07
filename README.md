# kubeplugin

1. Set up scripts/kubeplugin as Kubernetes plugin:
```bash
$ cd scripts
# make script executable
$ chmod 755 kubeplugin 
$ ls -la kubeplugin   
-rwxr-xr-x 1 dmitriy dmitriy 572 сер  7 13:14 kubeplugin

# copy to Kubernetes plugin folder
$ sudo cp ./kubeplugin /usr/local/bin/kubectl-kubeplugin

$ kubectl plugin list
The following compatible plugins are available:

/home/dmitriy/.krew/bin/kubectl-krew
/home/dmitriy/.krew/bin/kubectl-ns
/usr/local/bin/kubectl-kubeplugin
```

2. Use kubeplugin:
```bash
$ kubectl kubeplugin pod kube-system
pod, kube-system, coredns-576bfc4dc7-lplng, 3m, 13Mi
pod, kube-system, local-path-provisioner-6795b5f9d8-5567k, 1m, 7Mi
pod, kube-system, metrics-server-557ff575fb-vrg25, 6m, 21Mi
pod, kube-system, svclb-hello-world-2e461fcf-sn7kk, 0m, 0Mi
pod, kube-system, svclb-traefik-a4caba6c-hl5k7, 0m, 0Mi
pod, kube-system, traefik-5fb479b77-9nr4g, 2m, 27Mi

$ kubectl kubeplugin node kube-system

node, kube-system, k3d-asciiartify-server-0, 98m, 0%
```

3. Exception handling:
```bash
$ kubectl kubeplugin node 
Usage: /usr/local/bin/kubectl-kubeplugin <resource: node or pod> <namespace>
```