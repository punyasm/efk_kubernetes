# EFK on kubernetes
Log Analysis with Elasticsearch, Fluentd and Kibana (EFK) in Kubernetes Cluster. When running multiple applications and services on a Kubernetes cluster, a centralized, cluster-level logging stack can help in quickly sorting through and analysing the heavy volume of log data produced by the Pods. A popular centralized logging solution is the Elasticsearch, Fluentd, and Kibana (EFK) stack.


### Prerequisite
* Kubernetes cluster required

### Installation 

#### Step 1: Create Namespace and storage in K8 cluster
> kubectl create -f kube-logging.yaml
#### Step 2: Create StorageClass and PersistentVolume for EFK
> kubectl create -f efk-storage.yml
#### Step 3: Create StatefulSet Pods and services for elastic search cluster 
> kubectl create -f elasticsearch_svc.yaml
#### step 4: Create DaemonSet, ServiceAccount, ClusterRole for fluentd
> kubectl create -f fluentd.yaml
#### Step 5: Create service and deployment for Kibana
> kubectl create -f kibana.yml

### Note
Download all yml file from this repo.
