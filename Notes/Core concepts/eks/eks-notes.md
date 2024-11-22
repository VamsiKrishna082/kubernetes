TO update the kubectl to talk to eks cluster instead of minikube, first take backup of existing config which is in path 



aws eks --region us-west-2 update-kubeconfig --name <cluster-name>