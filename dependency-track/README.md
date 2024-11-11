## Install Dependency Tracker

```
helm repo add evryfs-oss https://evryfs.github.io/helm-charts/
helm repo update
kubectl create namespace dependency-track

helm install dependency-track --values deptrack.values.yaml --namespace dependency-track evryfs-oss/dependency-track
helm list -n dependency-track

# get the port of the service
kubectl get all -n dependency-track

# get the ip address
kubectl get ing -A

# edit the host file /etc/hosts, add the record
IPADDRESS dependencytrack.example.org

# access
http://dependencytrack.example.org

# default credentials
# user: admin
# pwd: admin
```