- kubernetes 101 - http://omerio.com/2015/12/18/learn-the-kubernetes-key-concepts-in-10-minutes/

**[Kubernetes Architecture](http://kubernetes.io/docs/admin/cluster-components)**

*Control plane*

- API server - for [services](https://github.com/kubernetes/kubernetes/wiki/Services-FAQ)
- etcd - distributed key-value store for cluster state (metadata)
- scheduler - watches newly created pods that have no node assigned, and selects a node for them to run on

- controller-manager
- a) node controller - health check nodes
- b) endpoints controller - populates the Endpoints object (i.e., join Services & Pods) 
- c) service account & token Controllers -  create default accounts and API access tokens for new namespaces
- d) [replication controller](http://kubernetes.io/docs/user-guide/replication-controller/) - [replicate](https://coreos.com/kubernetes/docs/latest/replication-controller.html) [pods](https://coreos.com/kubernetes/docs/latest/pods.html)

- kubectl (CLI for admin)

*Worker Node*

- kubelet (agent)
- kube-proxy - route networking and services[https://coreos.com/kubernetes/docs/latest/services.html] between control plane and worker nodes
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


