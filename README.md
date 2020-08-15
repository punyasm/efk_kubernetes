# efk on kubernetes
Log Analysis with Elasticsearch, Fluentd and Kibana (EFK) in Kubernetes Cluster. When running multiple applications and services on a Kubernetes cluster, a centralized, cluster-level logging stack can help in quickly sorting through and analysing the heavy volume of log data produced by the Pods. A popular centralized logging solution is the Elasticsearch, Fluentd, and Kibana (EFK) stack.

Elasticsearch is a real-time, distributed, and scalable search engine which allows for full-text and structured search, as well as analytics. It is commonly used to index and search through large volumes of log data but can also be used to search many different kinds of documents.Elasticsearch is commonly deployed alongside Kibana, a powerful data visualization frontend and dashboard for Elasticsearch; Kibana allows to explore the Elasticsearch log data through a web interface and build dashboards and queries to quickly answer questions and gain insight into the Kubernetes applications.

Fluentd is a popular open-source data collector, and is used to collect, transform, and ship log data to the Elasticsearch backend. It is set up to tail container log files, filter and transform the log data, and deliver it to the Elasticsearch cluster, where it will be indexed and stored.

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
