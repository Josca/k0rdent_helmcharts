# k0rdent extra service templates
Additional [k0rdent](https://k0rdent.github.io/docs/) supported service templates.

## Setup extra k0rdent objects
Setup extra helm repository and service templates using prepared manifests:
~~~bash
kubectl apply -f manifests # Configure a new k0rdent helm repository and service templates
kubectl get helmrepositories -A # Check repository was successfully added
kubectl get servicetemplate -A # Check service templates
~~~

## Use it in managed cluster
Update your managed cluster manifest `spec.services` section, e.g.:
~~~yaml
apiVersion: hmc.mirantis.com/v1alpha1
kind: ClusterDeployment
# ...
spec:
  services:
    - template: dapr-1-14-4
      name: managed-dapr
      namespace: dapr-system
# ...
~~~
