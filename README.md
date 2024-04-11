#install kubectl
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

#how to install minikube on linux
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube && rm minikube-linux-amd64
#start minikube
minikube start

#check the list of clusters
kubectl get nodes
#check minikube status
minikube status
#check kubernetes version
kubctl version
#check nodes
kubectl get node
#to get components
kubectl get services
#Create a pod
kubectl create deployment NAME --image=image [--dry-run] [options]
#sample: it will download nginx image from dockerhub
kubectl create deployment nginx-depl --image=nginx
#check deployment
kubctl get deployment
#check pods
kubctl get pod
#a layer between pod and deployment
kubctl get replicaset
#replicaset id managing the replicas of a pod
#edit deployment
kubctl edit deployment nginx-depl
#create deployment for mongodb
kubctl create deployment mongo-depl --image=mongo
#read logs
kubectl logs [pod name]
#describe shows more into
kubectl describe pod [pod name]
#get terminal of mongo db container
kubctl exec -it mongo-depl-rtrere-sfff -- bin/bash
#delete deployment : it wil delete replicaset and pod
kubctl delete deployment [name]
#use config file for all component options  and configs then apply it
kubctl apply -f [file name]
#sample
kubctl apply -f config-file.yaml
