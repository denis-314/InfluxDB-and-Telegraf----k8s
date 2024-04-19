Follow the below steps to deploy InfluxDB in Kubernetes using Helm charts and link it with Grafana.

PREREQUISITES:

    l. Kubernetes Cluster
    2. Copy the above YAML file on a local directory
    2. Open communication on ports 30015 on the Router (or other ports, but they need to be changed in the serice).

DEPLOYMENT STEPS:

  l. Add the helm official repository for Prometheus and Grafana 

    helm repo add stable https://charts.helm.sh/stable
    helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
    
  2. Create namespace
     
    kubectl create namespace prometheus
