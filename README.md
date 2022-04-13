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

### Run the first kubernetes command
