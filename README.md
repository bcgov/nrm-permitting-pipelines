# nrm-permitting-pipelines

Build and run locally: 
```sh
docker build -t pipeline-test:<tag> .
```

```sh
docker run --name pipeline-test pipeline-test
```

Create OpenShift ConfigMap: 
```sh
oc create configmap rrs-pipeline --from-file=rrs_extract.json
```

Push/pull from OpenShift Image Registry: 
```sh
oc registry login
```
```sh
docker push image-registry.apps.emerald.devops.gov.bc.ca/a1b9b0-dev/pipeline-test:<tag>
```
```sh
docker pull image-registry.apps.emerald.devops.gov.bc.ca/a1b9b0-dev/pipeline-test:<tag>
```
