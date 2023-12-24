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
  - Port: *
- Restautant Service
  - Deployed with postgreSQL DB
  - Port: 8083
- Camunda Service
  - Port: *
