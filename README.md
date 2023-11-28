# k8s Config Deploy Manager
This repository handles the deployment for our complete system. We are using ArgoCD for our automatic deployment. All the individual services will handle it's own image upload to Docker Hub in their CI/CD pipeline implementation (Most likely to be executed with Github Actions). 
