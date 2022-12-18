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


## labels

### docker
kubectl run alpaca-prod --image=gcr.io/kuar-demo/kuard-amd64:blue -- replicas=2 --labels="ver=1,app=apaca,env=prod"
kubectl run alpaca-test --image=gcr.io/kuar-demo/kuard-amd64:blue -- replicas=1 --labels="ver=2,app=apaca,env=test"
kubectl run bandicoot-prod --image=gcr.io/kuar-demo/kuard-amd64:blue -- replicas=2 --labels="ver=2,app=bandicoot,env=prod"
kubectl run bandicoot-staging --image=gcr.io/kuar-demo/kuard-amd64:blue -- replicas=1 --labels="ver=2,app=bandicoot,env=staging"

kubectl get deployments --show-labels
kubectl label pods alpaca-test "canary=true"
kubectl get pods -L canary

kubectl delete pods/alpaca-prod
kubectl delete pods/alpaca-test
kubectl delete pods/bandicoot-prod
kubectl delete pods/bandicoot-staging

