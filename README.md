# Install cert-manager

```shell
oc new-project cert-manager
helm template ./charts/cert-manager --namespace=cert-manager --name cert-manager --set image.tag=v0.6.2 | oc apply -f -
```

Once cert-manager is deployed you can run the below example.

This example will create a self-signed certificate issuer. 
This issuer will be the used to issue a self signed certifcate of type CA, i.e. a RootCA.
This rootCA is then used to create a CA type issuer.
This issuer is the used to create a leaf certifciate for a service.

```shell
oc apply -f RootCA-example.yaml
```