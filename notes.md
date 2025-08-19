# kubernetes allows you to create containers on different servers, either physical or virtual.And all of that is done automatically without your intervention.
# kubernetes takes care of the ...
  - automatic deployment of the containerized applications across different servers.
  - distribution of the load acros multiple servers.
  - auto-scaling of the deployed applications.
  - monitoring and health check of the containers
  - replacement of the failed containers.

# POD
  is the smollest unit in the k8s world. containers are created inside the pod
  POD involves
  - cantainer or containers
  - shared volumes
  - shared IP address

Note : one POD one server (not multiper server)
# Nod
  means server
# K8s
  - nodes (master node - worker nodes)
    + pods
      . containers
# k8s service 
  - master node
    kublet
    kube-proxy : is precent on each node , is responcible for network communication inside of each node and between nodes.
    container runtime : runs actual container inside of each node.
    API Server : is main point of communication between diffrent modes in the k8s world.
# minikube
  an app for create k8s cluster in local machine. it creats k8s cluster with single node which will be both worker and mater node.
