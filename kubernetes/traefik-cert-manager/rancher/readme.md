Running rancher without using values.yaml.
I purposely want to use rancher self signed cert. 

Testing.
helm install rancher rancher-latest/rancher \
  --namespace cattle-system \
  --set hostname=rancher.kube.bladerose.me \
  --set ingress.tls.source=rancher \
  --set bootstrapPassword=admin
