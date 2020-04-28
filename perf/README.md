# Perf test mongodb
This document performs a benchmarking on a single mongodb replicaset in a given environment.

## Tool
This test uses a dockerized version of [mongo-perf](https://github.com/mongodb/mongo-perf) which is also rolled into a kubernetes deployment.

## Deploy
```
kubectl apply -f mongo-perf.yaml
```

## Usage