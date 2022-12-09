docker run -d --name kuard --publish 8080:8080 --memory 200m --memory-swap 1G --cpu-shares 1024 gcr.io/kuar-demo/kuard-amd64:blue



az login
az account show --output table

# create cluster
az group create --name=kuar --location=northeurope
az aks create --resource-group=kuar --name=kuar-cluster --generate-ssh-keys
az aks get-credentials --resource-group=kuar --name=kuar-cluster
az aks install-cli


# kubectl
az aks get-credentials --resource-group=kuar --name=kuar-cluster

path variables
C:\Users\paul\.azure-kubectl
C:\Users\paul\.azure-kubelogin
az aks install-cli

kubectl get nodes
kubectl describe nodes aks-nodepool1-19386622-vmss000000