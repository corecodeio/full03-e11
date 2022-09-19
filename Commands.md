# Nodes
kubectl get nodes

# Namespaces
kubectl get ns
kubectl create ns app1
kubectl delete ns app1

# Deployment
kubectl create deployment hello --image=k8s.gcr.io/echoserver:1.4

kubectl get pods
kubectl get pods -A

# Servicio
kubectl expose deployment hello --type=NodePort --port=8080
kubectl expose deployment hello --type=LoadBalancer --port=8080

kubectl get services
kubectl delete service hello

## Apply Manifest

kubectl apply -f .\pod.yaml
kubectl apply -f .\deployment.yaml