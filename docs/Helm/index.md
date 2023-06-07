# Helm

[Helm](http://helm.sh) is a package manager for kubernetes. Install helm  
using a package manager.

``` code
brew install helm
```

## Add a Chart repository

The [Artifact Hub](https://artifacthub.io) is a repository for the charts.

``` code
helm repo add bitnami https://charts.bitnami.com/bitnami
```

Check if the repo was added

``` code
helm repo list
```

## Get Nginx from the repository

Search the repository for nginx

``` code
helm search repo nginx
```

Get all the versions

``` code
helm search repo --versions nginx
```

``` code
helm search repo --versions "web server"
```

Get k8s config contexts

``` code
kubectl config get-contexts
```

## Install the chart throug Helm

Don't install helm in the default namespace  
Create a new one

``` code
kubectl create ns web
```

Change the context to the new namespace

``` code
kubectl config set-context --current --namespace=web
```

Install the helm chart. You need to supply name. Multiple instances can be installed.

``` code
helm install nginx01 bitnami/nginx
```

Result

``` code
NAME: nginx01
LAST DEPLOYED: Wed Jun  7 06:52:59 2023
NAMESPACE: web
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
CHART NAME: nginx
CHART VERSION: 15.0.1
APP VERSION: 1.25.0

** Please be patient while the chart is being deployed **
NGINX can be accessed through the following DNS name from within your cluster:

    nginx01.web.svc.cluster.local (port 80)

To access NGINX from outside the cluster, follow the steps below:

1. Get the NGINX URL by running these commands:

  NOTE: It may take a few minutes for the LoadBalancer IP to be available.
        Watch the status with: 'kubectl get svc --namespace web -w nginx01'

    export SERVICE_PORT=$(kubectl get --namespace web -o jsonpath="{.spec.ports[0].port}" services nginx01)
    export SERVICE_IP=$(kubectl get svc --namespace web nginx01 -o jsonpath='{.status.loadBalancer.ingress[0].ip}')
    echo "http://${SERVICE_IP}:${SERVICE_PORT}"
```



## Examine what was installed

Use the kubectl to see what was installed

``` code
kubectl get all
```

## Upgrade the Chart installation

Install a different version of nginx in the default namespace

``` code
helm install nginx02 --version 13.1.5 -n default bitnami/nginx
```

See if the pod was installed

``` code
kubectl get pods -n default
```

Open shell to the pod

``` code
kubectl -n default exec -it nginx02-64cbd99d9b-kmnbh bash
```

Run the following command inside the pod

``` code
nginx -v
```

Get services in defaut namespace  

``` code
kubectl get svc -n default
```

Change the Port type and number. Go to the artifact hub to get the parameters (values).  

There is two ways to change the values, yaml and --set command


``` yaml
service:
  type: NodePort
```

Install the helm chart with the values

``` code
helm install nginx03 --values values.yaml --set service.ports.http=8080 bitnami/nginx
```

Examine the service

``` code
kubectl get svc nginx03
```

## Remove the installation from the cluster

View all the installations in current namespace

``` code
helm list
```

View all installations
``` code
helm list --all-namespaces
```

Upgrade

``` code
helm upgrade nginx01 --set service.ports.http=8081 bitnami/nginx
```

Reuse values

``` code
helm upgrade nginx01 --set service.ports.http=8081 --reuse-values bitnami/nginx
```

Uninstall installations in current namespace

``` code
helm uninstall nginx01
```

Uninstall installations in default namespace

``` code
helm uninstall nginx02 -n default
```