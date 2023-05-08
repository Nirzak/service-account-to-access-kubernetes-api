# service-account-to-access-kubernetes-api
Just clone this repo and run the commands to get a read only service account on kubernetes that can be used to access kubernetes API

## Run the following commands sequentially to get everything ready

```
kubectl apply -f account.yml
```

```
kubectl apply -f clusterrole.yml
```
```
kubectl apply -f rolebinding.yml
```

```
kubectl apply -f secret.yml
```

This will create a service account on monitoring namespace on kubernetes cluster and will only have read only access to the cluster.

To get the sercret token of this service account to access the cluster, Run the following command:

```
kubectl describe secrets/<our_token_name> -n monitoring
```
