Follow the below steps to deploy InfluxDB in Kubernetes using Helm charts and link it with Grafana.

PREREQUISITES:

    l. Kubernetes Cluster
    2. Copy the above YAML file on a local directory
    2. Open communication on ports 30015 on the Router (or other ports, but they need to be changed in the serice).

DEPLOYMENT STEPS -- INFLUXDB --

  1. Create the local directory used for persistent volumes on all Kubernetes nodes

    cd /home/kube
    mkdir influxdb-files
    cd influxdb-files
    mkdir volume-files
    
  2. Edit the Persistent Volume section inside influxdb_deployment_all.yaml to reflect the path to the folder defined at step. 1
  3. Create the InfluxDB Deployment

    kubectl apply -f influxdb_deployment_all.yaml

  3. Acces InfluxDB web UI on port 30015 in browser

Bibliography:
  - https://opensource.com/article/19/2/deploy-influxdb-grafana-kubernetes
  - https://medium.com/@nikhil.nagarajappa/installing-influxdb-in-k8s-2fe0e0647431

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

DEPLOYMENT STEPS -- TELEGRAF --

  1. Create the local directory for the yaml files

    cd /home/kube
    mkdir telegraf-files
    cd telegraf-files

  2. Edit the ConfigMap section inside telegraf_deployment_all.yaml to reflect the correct address and credentials of vCenter and InfluxDB
  3. Create the Telegraf Deployment
     
    kubectl apply -f telegraf_deployment_all.yaml

_____________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________

Additional information

- Add new InfluxDB Data Source in Grafana: https://www.youtube.com/watch?v=Jszd7zrl-_U
  
- For vSphere Dashboards go to: https://grafana.com/grafana/dashboards/8159-vmware-vsphere-overview/
     - VMware vSphere - Overview -> ID 8159
     - VMware vSphere - VMs -> ID 8168
     - VMware vSphere - Hosts -> ID 8165
     - VMware vSphere - Datastore -> ID 8162
