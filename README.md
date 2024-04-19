Follow the below steps to deploy InfluxDB in Kubernetes using Helm charts and link it with Grafana.

PREREQUISITES:

    l. Kubernetes Cluster
    2. Copy the above YAML file on a local directory
    2. Open communication on ports 30015 on the Router (or other ports, but they need to be changed in the serice).

DEPLOYMENT STEPS:

  l. Create the local directory used for persistent volumes on all Kubernetes nodes

    cd /home/kube
    mkdir influxdb-files
    cd influxdb-files
    mkdir volume-files
    
  2. Create the Storage Class and the Persistemt Volume
     
    kubectl apply -f influxdb-persistent-volume.yaml
   
  3. Create the InfluxDB Deployment

    kubectl apply -f influxdb-deployment.yaml
