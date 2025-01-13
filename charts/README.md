# How to update helm repo content

~~~bash
helm dependency update dapr # Download given chart deps, build <chart>/Chart.lock file
helm package dapr # Build chart package (.tgz file)
helm repo index --url https://Josca.github.io/k0rdent_helmcharts/charts . # update index.yaml
~~~
