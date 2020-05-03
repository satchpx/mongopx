# Benchmarking mongo with and without px

## Install MongoDB without PX

### Install Mongo

*NOTE:* We shall be installing a single replicaset of Mongo.
@TODO: Install sharded mongo cluster

```text

helm repo add bitnami https://charts.bitnami.com/bitnami
helm search repo bitnami
helm install --name mongodb --namespace mongodb --values ../../manifests/mongodb-values-nopx.yaml bitnami/mongodb
```

### Test

For running Load/ Stress/ Perf tests on MongoDB, refer [here](https://github.com/satchpx/mongopx/tree/master/perf)