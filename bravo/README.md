# Bravo

## Game of pods

First create the directory on the node

```bash
ssh node01 mkdir /drupal-data /drupal-mysql-data
```

Create the manifest files and then apply then with `kubectl apply -f`

## Kind Cluster

If you're running kind with docker, you can execute the following commands

```bash
git clone  git@github.com:jbuet/gameofpods.git && cd gameofpods/
kind create cluster
docker exec -it kind-control-plane sh -c 'mkdir /drupal-data /drupal-mysql-data'
kubectl apply -f bravo/
kubectl port-forward svc/drupal-service 8080:80
```
