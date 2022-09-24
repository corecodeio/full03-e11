# Kubernetes Resources

This folder contains the k8s objects to start your JavaScript Example Application. We use kustomize to create the objects quickly in one command.

## How to use it

The following command creates all the necessary resources to start the application.

``` bash
cd k8s

# Create env file for database credentials
cat <<EOF >.env
sys-pass=mysyspassword
app-pass=myapppassword
EOF

# Create K8s objects
kubectl apply -k k8s/
```
## Useful Commands

``` bash
# Nodes
kubectl get nodes

# Namespaces
kubectl get ns
kubectl create ns app1
kubectl delete ns app1

# Deployments
kubectl create deployment hello --image=k8s.gcr.io/echoserver:1.4

# Pods
kubectl get pods
kubectl get pods -A
kubectl get pods -n mynamespace
kubectl describe pods -n mynamespace
kubectl logs <pod_name> -n mynamespace

# Services
kubectl expose deployment hello --type=NodePort --port=8080
kubectl expose deployment hello --type=LoadBalancer --port=8080
kubectl get services -A
kubectl delete service hello

# Apply Manifest (Declarative Way!!)
kubectl apply -f frontend.yaml

# Apply Kustomization
kubectl apply -k <folder>
```
