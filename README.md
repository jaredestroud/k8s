### K8s Cheatsheet

#### List K8s Objects
```
kubectl get $OBJECT (pods/deployments/services/etc...)
```

### Create K8s Objects 
* note, this is not the same as "kubectl apply" which is recommended for k8s declarative language.
```
kubectl create -f deployment.yml
```
or
```
kubectl run --image gcr.io/archcloudlabs/app-1 --namespace app-1 NAME_OF_POD       
```

### Namespaces
* Get all namespaces (3 by default)
```
kubect get namespaces
```
* Set namespace
```
kubectl config set-context --current --namespace=<insert-namespace-name-here>
```

### Pods

* Get Pod Logs
```
kubectl logs my-pod
```

* Interact with deployed pod
```
kubectl exec -it my-pod CMD_TO_RUN
```

### Deployments
* List Deployments
```
kubectl get deployment
```
* Scale Deployment
```
kubectl scale deployment $DEPLOYMENT_NAME --replicas=8
```

### Services
* Expose service to a deployment
```
 kubectl expose deployment hello-world --type=LoadBalancer --name=my-service
```