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
Install `dapr` using helm chart:
~~~bash
helm install dapr k0rdent-extra/dapr --namespace dapr-system --create-namespace
~~~
