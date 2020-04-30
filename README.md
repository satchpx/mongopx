# mongopx
Running MongoDB on Kubernete

## Install

### Install helm
```
https://github.com/helm/helm/blob/master/docs/install.md
```

### Initialize helm
```
helm  init
kubectl create serviceaccount --namespace kube-system tiller
kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
kubectl patch deploy --namespace kube-system tiller-deploy -p '{"spec":{"template":{"spec":{"serviceAccount":"tiller"}}}}'
```

### Create the required storageClasses
```
kubectl apply -f manifests/portworx-storageclasses.yaml
kubectl apply -f manifests/mongo-px-sc.yaml
```

### Install Mongo
*NOTE:* We shall be installing a single replicaset of Mongo.
@TODO: Install sharded mongo cluster
```
helm repo add bitnami https://charts.bitnami.com/bitnami
helm search repo bitnami
helm install --name mongodb --namespace mongodb --values manifests/mongodb-values.yaml bitnami/mongodb
```

### Test
For running Load/ Stress/ Perf tests on MongoDB, refer [here](https://github.com/satchpx/mongopx/tree/master/perf)