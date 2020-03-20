## Prerequisties
The TripInsights sql database to connect to.
Ingress in your cluster (script below)


kubectl create namespace tripinsights
kubectl create namespace tripinsights-ingress
helm install tripingress stable/nginx-ingress --namespace tripinsights-ingress

#Now grab the External-IP and use it in the helm chart.

helm install --set ingressControllerIP=1.2.3.4 tripapp . -n tripinsights
