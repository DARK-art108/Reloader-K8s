### Reload ConfigMap and Secret Automatically

This repo contians a poc on making use of reloader components this will keep a watch on configmaps and secret and reload automatically when their is a change in them.

## Setup

1. ```helm repo add stakater https://stakater.github.io/stakater-charts```
2. ```helm repo update```
3. ```helm install reloader stakater/reloader # To watch CM/secrets in all namespaces```
4. ```helm install reloader stakater/reloader --set reloader.watchGlobally=false --namespace NAMESPACENAME # To watch CM/Secrets in one namespace```
5. ```kubectl apply -f https://raw.githubusercontent.com/stakater/Reloader/master/deployments/kubernetes/reloader.yaml```
6. ```kubectl apply -k https://github.com/stakater/Reloader/deployments/kubernetes```

NOTE: **By default, Reloader gets deployed in the default namespace and watches changes secrets, and configmaps in all namespaces.**