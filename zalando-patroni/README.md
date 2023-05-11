# Zalando patroni

## Installer Helm
### Install from source helm
```shell script
sudo apt -y install build-essential
sudo snap install go --classic
wget https://github.com/helm/helm/archive/refs/tags/v3.11.3.tar.gz
tar -zxvf v3.11.3.tar.gz
cd helm-3.11.3/
make
cd bin
sudo cp  helm /usr/local/bin/helm
helm version
```
## Patroni operator
### add repo for postgres-operator
```shell
helm repo add postgres-operator-charts https://opensource.zalando.com/postgres-operator/charts/postgres-operator
```
### install the postgres-operator
```shell
helm install postgres-operator postgres-operator-charts/postgres-operator
```
### add repo for postgres-operator-ui
```
helm repo add postgres-operator-ui-charts https://opensource.zalando.com/postgres-operator/charts/postgres-operator-ui
```
### install the postgres-operator-ui
```
helm install postgres-operator-ui postgres-operator-ui-charts/postgres-operator-ui
```

## Check 
```
kubectl get pod -l app.kubernetes.io/name=postgres-operator
```

