https://kubernetes.io/docs/tutorials/kubernetes-basics/
https://medium.com/@shoaib_masood/metallb-network-loadbalancer-minikube-335d846dfdbe
https://medium.com/faun/metallb-configuration-in-minikube-to-enable-kubernetes-service-of-type-loadbalancer-9559739787df
https://github.com/t0mm4rx/ft_services

Docker install:
Brew install docker
Brew install docker-machine
Install virtual box
Script

__NOTES__

First have a kubernetes cluster, after you can deploy your containers on it.
For this you need to create deployment and then expose it publicly via a service.

To deploy your containers, you need a kubernetes deployment configuration, this will instruct the master node how to create and update. This will constantly monitor the containers, if one container goes down it replaces it with another node, allowing recovery from machine failure.
To create one you need to use Kubectl, it uses the kubernetes api to interact with the cluster.

A node is a worker machine, each node is managed by the kubernetes master. Each node contains one or more pods.
Every kubernetes node runs at least;
-Kubelet, a process responsible for communication between node and master, it manages the pods and containers on a machine.
-A container runtime like docker (that sits in a pod), responsible for unpacking the container, pulling the container image and running the application.

A pod is a group of one or more containers that have shared resources, like IP address and port. By creating a deployment pods are created.
Each pod is tied to a node until termination. In case of a failure identical pods are scheduled on other nodes.

A service is a grouping of pods, the set of pods is determined by a LabalSelector. Services allow you to receive traffic and can be exposed in different ways for example through a load balancer.
The load balancer assigns a fixed external IP ti the service, allowing you to not exposing the nodes themselves and giving one endpoint (entry point).


TODO:
- Master node / Deployment - kubectl
- Node
- Service - LabelSelector - Loadbalancer
- Pod - YAML
- Container - Docker
- Img

HOW TO RUN MULTIPLE INSTANCES - Not necessary for ft_service
For increased traffics calling is necessary, this is done through changing the number of replicas.

