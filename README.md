# Deep South Devs Kubernetes Demo

This repo houses some of the files that were used to demo kubernetes at a Deep South Devs Meetup in March 2022. 

While the demo demonstrated a number of different kubernetes features, such as deployments of pods, cronjobs, services, hpa scaling etc, and that on a kubernetes cluster spun up on GCP, this files will bring up only a subset of the services and subset of k8s functionality demo'd on a minikube VM. 

## Steps
### Install kubectl 
- kubectl is the kubernetes command line tool that allows you to run commands against kubernetes clusters.
- Install it by following the instructions listed [here](https://kubernetes.io/docs/tasks/tools/)


### Install Minikube
- Minikube is a local kubernees that allows for easy learning and development on kubernetes. In our case it will be great since it runs on your local machine and costs nothing. To install, follow instructions listed [here](https://minikube.sigs.k8s.io/docs/start/)
- start minikube if not started already. Run `minikube start` in the terminal
- `minikube start` should point your kubectl to the minikube cluster. If you already using kubectl for other things like work, be careful and check that kubectl is pointing to the minikube cluster before continuing. 

### Use kubectl to spin up mysql
- Run `kubectl apply -f mysql/data-persistentvolumeclaim.yaml` to create a persistent volume claim which will be used by the mysql pod
- Run `kubectl apply -f mysql/mysql-deployment.yaml` to create a mysql pod. 
- Run `kubectl apply -f mysql/mysql-service.yaml` to allow the myql pod to be reachable throughout the cluster (remember a cluster could have more than one node and the POD can be deployed to any node belonging to the cluster. Of course in minikube case there will only be 1, but this will definitely not be the case in reality).
- You can run `kubectl get pods` to see if the pod has started successfuly. Similarly run `kubectl get services` and `kubectl get pvc` to check the services and private volume claim respectively.  Note that the POD may take quite long to spin up since it has to download the mysql image for the first time. 

### Use kubectl to spin up the church-auth module
- Run `kubectl apply -f church-auth/church-auth-deployment.yaml` to create a church auth pod
- Run `kubectl apply -f church-auth/church-auth-service.yaml` to allow the church-auth pod to be accessible to others.
- You can run `kubectl get pods` to see if the pod has started successfuly. Similarly run `kubectl get services`  to check the services.  Note that the POD may take quite long to spin up since it has to download the mysql image for the first time. 

