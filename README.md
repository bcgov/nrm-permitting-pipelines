# nrm-permitting-pipelines

Build locally: 
```sh
docker build -t image-registry.apps.emerald.devops.gov.bc.ca/a1b9b0-dev/pipeline-test:<tag> .
```

Push to OpenShift Image Registry: 
```sh
oc registry login
```
```sh
docker push image-registry.apps.emerald.devops.gov.bc.ca/a1b9b0-dev/pipeline-test:<tag>
```

Create OpenShift ConfigMap: 
```sh
oc create configmap <config map name> --from-file=extract.json
```

Get the latest SHA for the image: 
```sh
oc describe imagestream pipeline-test 
```

Deploy (make sure to update the SHA): 
```sh
oc apply -f deployment.yaml
```
