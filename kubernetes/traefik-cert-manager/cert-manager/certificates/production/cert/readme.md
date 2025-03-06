## Kube tls.secretName:
NAME                READY   SECRET                  AGE
kube-bladerose-me   True    kube-bladerose-me-tls   114m

## Extracting from secrets from: 
`k get certificate -n default` 

SResult:
```bash
kubectl get secret kube-bladerose-me-tls -n default -o jsonpath='{.data.tls\.crt}' | base64 -d > cert.pem
kubectl get secret kube-bladerose-me-tls -n default -o jsonpath='{.data.tls\.key}' | base64 -d > key.pem
```

## Check the certificate: and key:
```bash
openssl x509 -in cert.pem -text -noout
openssl rsa -in key.pem -check
```
