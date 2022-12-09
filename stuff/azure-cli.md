# Azure cli commands

## login
az login
az account show --output table

## create cluster
az group create --name=kuar --location=northeurope
az aks create --resource-group=kuar --name=kuar-cluster --generate-ssh-keys