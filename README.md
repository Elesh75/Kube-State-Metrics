# Kube-State-Metrics
Integrating KSM with Prometheus
        
        Installation:
You typically deploy kube-state-metrics as a Kubernetes service and expose its metrics for consumption by monitoring tools like Prometheus.
                
                kubectl apply -f https://github.com/kubernetes/kube-state-metrics/releases/latest/download/kube-state-metrics-deployment-standard.yaml

This creates the necessary resources for kube-state-metrics in your cluster.

kube-state-metrics is an open-source project that generates metrics about the state of Kubernetes objects in a cluster. 
It extracts and exposes these metrics in a format that can be consumed by monitoring and alerting systems. 
The metrics provided by kube-state-metrics give insights into the health and performance of the Kubernetes cluster.

Key Features:

Object Metrics:

kube-state-metrics collects metrics related to the state and health of various Kubernetes objects, 
including nodes, pods, services, deployments, and more.

Resource Utilization:
It provides information about resource utilization, such as CPU and memory usage, for pods and nodes.

Desired vs. Current State:
Metrics are exposed to compare the desired state of objects (as defined in YAML manifests)
with their current state in the cluster.

Label-based Metrics:
kube-state-metrics supports label-based metrics, allowing for more granular 
monitoring and alerting based on labels attached to Kubernetes objects.

Prometheus Integration:
It is commonly used in conjunction with Prometheus, a popular monitoring and alerting 
toolkit for containerized environments.

Use Cases:
Monitoring and Alerting:
Provides insights into the overall health of the cluster and helps detect issues or anomalies.

Capacity Planning:
Metrics related to resource utilization aid in capacity planning and optimization.

Automation and Scaling:
Can be used to automate scaling decisions based on the observed state of the cluster.

   Example Query:
Here's an example Prometheus query that uses kube-state-metrics metrics to get the current number of running pods for a specific deployment:
     kube_deployment_status_replicas_available{deployment="your-deployment-name"}
