docker run -d --name kuard --publish 8080:8080 --memory 200m --memory-swap 1G --cpu-shares 1024 gcr.io/kuar-demo/kuard-amd64:blue



az login
az account show --output table

# create cluster
az group create --name=kuar --location=northeurope
az aks create --resource-group=kuar --name=kuar-cluster --generate-ssh-keys