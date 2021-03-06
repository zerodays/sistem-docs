## Kubernetes deployment

How to add new microservice to Microsoft Azure cloud.

#### Azure tools installation

Install Azure Cloud Shell tool and `kubectl`.
```
sudo apt install azure-cli
sudo az aks install-cli

# login into azure
az login
```

Set correct resource group and cluster.
```
az aks get-credentials --resource-group "sistem-resource-group" --name "sistem-cluster"
# check if this is correct cluster
kubectl get nodes
```

#### New deployment creation

Create new `.yaml` file, similar to ones from the lectures, see [this link](https://github.com/prporso2021/rso-image-catalog/blob/master/k8s/image-catalog-deployment.yaml).


Deploy:
```
kubectl apply -f kubernetes_deployment.yaml

# List all services
kubectl get services
# See logs for a service
kubectl logs service-name
```

##### Useful commands
SSH to a pod (container if there is only one container in a pod).
```
kubectl exec --stdin --tty pod-name -- /bin/bash
```
Get logs in specific container:
```
kubectl logs pod-name -c container-name
```

#### Ingress

Followed tutoral from [here](https://docs.microsoft.com/en-us/azure/aks/ingress-basic) which has a problem described [here](https://github.com/MicrosoftDocs/azure-docs/issues/47395). Problem still exists but can be fixed using command from [here](https://stackoverflow.com/questions/61365202/nginx-ingress-service-ingress-nginx-controller-admission-not-found).

Get Ingress information
```
kubectl get services -o wide -w nginx-ingress-ingress-nginx-controller
```
