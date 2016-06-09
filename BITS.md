- kubernetes 101 - http://omerio.com/2015/12/18/learn-the-kubernetes-key-concepts-in-10-minutes/

**Kubernetes Architecture**

1. control plane 

- API server - for services
- etcd - distributed key-value store for cluster state (metadata)
- scheduler - schedule pod to worker node
- replication controller - replicate pods
- kubectl (CLI for admin)

2. worker node (physical/VM) 

- kubelet (agent)
- kube-proxy - networking between control plane and worker nodes
- container runtime (Docker, rkt, etc)

**Machine**

- has an IP address
- optional port
- stateless (application machine or containers)
- stateful (system machine)

**System machine vs Application machine**

- system machine - physical or virtual machine (OS, config mgmt, hypervisor, SSH, mutable)
- application machine - containers may or may not have OS inside (managed by Docker, Kubernetes, immutable)



- when a container crashes, [kubelet](http://kubernetes.io/docs/user-guide/volumes) will restart it
- types of volumes (http://kubernetes.io/docs/user-guide/volumes)
- example of label: tier=frontend, app=myapp
- example of label: tier=backend, app=myapp
- replication controller: pod template + label
- service - load balance two or more pod replicas

**NSQ on Kubernetes**

- https://github.com/ibmendoza/nsq-kubernetes
- http://www.hward.com/nsqd-service-discovery-with-dns-records
- https://gist.github.com/bketelsen/a2d353d0318736c9fa23


