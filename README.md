# k8s Config Deploy Manager
This repository handles the deployment for our complete system. We are using ArgoCD for our automatic deployment. All the individual services will handle it's own image upload to Docker Hub in their CI/CD pipeline implementation (Most likely to be executed with Github Actions). 

## Services 
Services that needs to be exposed are done wtih load balancer and Nginx Ingress. Secrets are are created with Sealed Secrets.

- Auth Service
  - Deployed with postgreSQL DB
  - Port: 8086
- Webpage (React)  
  - Port: 3000
- RabbitMQ Server
  - Port: 5672
- Restautant Service
  - Deployed with postgreSQL DB
  - Port: 8083
- Camunda Service
  - Port: 8087
- Camel Service
  - Port: 8081
- Order Service
  - Deployed with postgreSQL DB
  - Port: 8084

## Secrets
We are using Sealed Secrets to pass secret information such as usernames and password to our application

## Reverse proxy and loadbalancer
We are using NGINX Ingress controller as our reverse proxy and loadbalancer. 
The webpage will have the path "/", and our backend api's are using the "/api/*service" path. 

## Cluster and nodes
We have 2 nodes, each on their own cluster.
- 2 Cluster
- 2 Nodes

![Cluster and nodes](https://raw.githubusercontent.com/noInPuts/k8s-config-deploy-manager/main/pictures/kubernetes_2.png)
![Deployment architecture on kubernetes](https://raw.githubusercontent.com/noInPuts/k8s-config-deploy-manager/main/pictures/kubernetes_1.png)
