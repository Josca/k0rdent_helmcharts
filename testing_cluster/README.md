# Test charts locally in "kind" cluster

## Setup
Create local testing cluster
~~~bash
kind create cluster --config testing_cluster/kind-cluster.yaml -n testing-cluster
~~~

Add `k0rdent-extra` helm charts repo:
~~~bash
helm repo add k0rdent-extra https://josca.github.io/k0rdent_helmcharts/charts/
helm search repo k0rdent-extra # check repo content
~~~

## Usage

### Install 'nginx-ingress-f5'
Install `nginx-ingress-f5` using helm chart:
~~~bash
helm install nginx-ingress-f5 k0rdent-extra/nginx-ingress-f5 --namespace nginx-ingress-f5 --create-namespace --set nginx-ingress.controller.hostPort.enable=true
~~~

### Install 'dapr'
Install `dapr` using helm chart:
~~~bash
helm install dapr k0rdent-extra/dapr --namespace dapr-system --create-namespace
kubectl apply -f testing_cluster/ingress-dapr.yaml
~~~
