# Kubernetes Voting App Deployment

This repository contains the configuration files and steps to deploy a simple voting app on a Kubernetes cluster. The app consists of multiple components, including a frontend, backend, database, and a worker service.


## Prerequisites

Before you begin, ensure you have the following tools installed:

- [Minikube](https://minikube.sigs.k8s.io/docs/start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)

## Usage

1. Start your Minikube cluster:

   ```bash
   minikube start
   ```
2. Deploy the components:
```bash
 kubectl create -f postgres-pod.yaml
      
      kubectl create -f postgres-service.yaml
      
      kubectl create -f redis-pod.yaml
      
      kubectl create -f redis-service.yaml
      
      kubectl create -f voting-app-pod.yaml
      
      kubectl create -f voting-app-service.yaml
      
      kubectl create -f result-app-pod.yaml
      
      kubectl create -f result-app-service.yaml
      
      kubectl create -f worker-app-pod.yaml
      # If applicable, create services for the worker app as well.
```
3. Verify the deployment:
```bash
kubectl get pods,svc
```
4. Access the services:
Voting app:
```bash
minikube service voting-service --url
```
Result app:
```bash
minikube service result-service --url
```

# End product
![image](https://github.com/KarkiAnmol/k8s-voting-app-deploy/assets/97075159/3f3c5fc4-d637-4ba1-bdd2-33f7f09b698d)
![image](https://github.com/KarkiAnmol/k8s-voting-app-deploy/assets/97075159/8f6a9a4b-44d8-4ca5-beea-28e000cf7157)

# Cleanup

To remove the deployed resources and stop Minikube, you can run:

```bash
kubectl delete -f postgres-pod.yaml
kubectl delete -f postgres-service.yaml
kubectl delete -f redis-pod.yaml
kubectl delete -f redis-service.yaml
kubectl delete -f voting-app-pod.yaml
kubectl delete -f voting-app-service.yaml
kubectl delete -f result-app-pod.yaml
kubectl delete -f result-app-service.yaml
kubectl delete -f worker-app-pod.yaml
# If applicable, delete services for the worker app as well.

minikube stop
```
# Troubleshooting

If you encounter any issues, please refer to the [Minikube documentation](https://minikube.sigs.k8s.io/docs/start/) or create a GitHub issue for assistance.

# Contributing

Feel free to contribute to this project by creating pull requests or reporting issues.

# License

This project is licensed under the MIT License.
