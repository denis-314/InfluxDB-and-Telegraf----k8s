Follow the below steps to deploy InfluxDB in Kubernetes using Helm charts and link it with Grafana.

PREREQUISITES:

    l. Kubernetes Cluster
    2. Copy the above YAML file on a local directory
    2. Open communication on ports 30015 on the Router (or other ports, but they need to be changed in the serice).

DEPLOYMENT STEPS INFLUXDB:

  1. Create the local directory used for persistent volumes on all Kubernetes nodes

    cd /home/kube
    mkdir influxdb-files
    cd influxdb-files
    mkdir volume-files
    
  2. Create the Storage Class and the Persistemt Volume
     
    kubectl apply -f influxdb-persistent-volume.yaml
   
  3. Create the InfluxDB Deployment

    kubectl apply -f influxdb-deployment.yaml

  4. Acces InfluxDB web UI on port 30015 in browser


DEPLOYMENT STEPS Telegraf:

  1. Create the local directory for the yaml files

    cd /home/kube
    mkdir telegraf-files
    cd telegraf-files
    
  2. Create the Telegraf Deployment
     
    kubectl apply -f telegraf_deployment_all.yaml

Bibliography:
  - https://opensource.com/article/19/2/deploy-influxdb-grafana-kubernetes
  - https://medium.com/@nikhil.nagarajappa/installing-influxdb-in-k8s-2fe0e0647431
