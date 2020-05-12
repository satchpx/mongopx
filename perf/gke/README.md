# Repro env in GKE

## Setup GKE

```text
gcloud container clusters create kroger-perf \
     --region us-central1 \
     --node-locations us-central1-b,us-central1-c,us-central1-f \
     --disk-type=pd-ssd \
     --disk-size=100GB \
     --labels=portworx=gke \
     --machine-type=e2-standard-16 \
     --num-nodes=1 \
     --image-type ubuntu \
     --scopes compute-rw,storage-ro \
     --enable-autoscaling --max-nodes=6 --min-nodes=3
```

```text
gcloud container clusters get-credentials kroger-perf
```

## Install Portworx

```text
kubectl create clusterrolebinding myname-cluster-admin-binding \
    --clusterrole=cluster-admin --user=`gcloud info --format='value(config.account)'`

kubectl apply -f 'https://install.portworx.com/2.3?mc=false&kbver=1.14.10&b=true&s=%22type%3Dpd-ssd%2Csize%3D1024%22&kd=type%3Dpd-standard%2Csize%3D150&c=px-cluster-f2b7355d-4af6-4c65-a49f-6946965f6081&gke=true&stork=true&lh=true&st=k8s'
```

### Setup Portworx CLI

```text
PX_POD=$(kubectl get pods -l name=portworx -n kube-system -o jsonpath='{.items[0].metadata.name}')
alias pxctl="kubectl exec $PX_POD -n kube-system -- /opt/pwx/bin/pxctl"
```

## Mongo loader

```text
kubectl run mongo-loader --image=ubuntu --restart=Always --command -- /bin/sleep infinity
kubectl exec -it mongo-loader-5b9cbbcd7d-ftzls bash
apt-get update
apt-get install vim git
apt install default-jre
apt install openjdk-11-jre-headless
apt install openjdk-8-jre-headless
java -version
git clone https://github.com/idealo/mongodb-performance-test.git
cd mongodb-performance-test/
java -jar $jarfile -m insert -o 1000000 -t 10 -db test -c perf -h mongodb.mongodb -port 27017 -u root -p 'Password1' -adb admin
```