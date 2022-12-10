# Azure cli commands

## login
az login
az account show --output table

## create cluster
az group create --name=kuar --location=northeurope
az aks create --resource-group=kuar --name=kuar-cluster --generate-ssh-keys

## pods

kubectl run kuard --image=gcr.io/kuar-demo/kuard-amd64:blue
kubectl run kuard --generator=run-pod/v1 --image=gcr.io/kuar-demo/kuard-amd64:blue

kubectl get pods
kubectl describe pods kuard
kubectl delete pods/kuard


kubectl apply -f kuard-pod.yaml
kubectl port-forward kuard 8080:8080


kubectl logs -f kuard

kubectl delete -f kuard-pod.yaml




