1. TO reach a pod and the container running in the pod , we need a service object.

2. service object is responsible for exposing pods to other pods in the cluster or to external world.(outside of cluster)

3. Pods by default has a internal IP Address, we cannot use this address to access the pod , it will changed whenever a pod is replaced.(we cannot rely on the pod ip address as it keeps on replaced due to scaling other factors.)

4. services groups pods together with a shared IP. services can allow external access to pods.

5. without services , pods are difficult to reach and communication is difficult.

Exposing a deployment with a service

1. to create a service , we can use kubectl create service command , but better than this we can use below command  ,for exposing the pod created by deployment.

kubectl expose deployment <deployment-name> --type=ClusterIP --port=8080

there are three types:

1. ClusterIP - by this we will get a static IP for the pod , but we wont be able to reach the pod from outside world , as it is cluster internal only can be accessed inside the cluster.

2. NodePort - Means this deployment should be exposed with the help of IP Address of worked node on which it is running , this then accessible to outside world.

3. LoadBalancer - utilizes a loadbalancer , which has to exist in the infrastructure on where this cluster runs , the the loadbalancer will generate a unique ip address for this service which then accesssible to outside world, apart from this as name implies it also evenly distribute traffic evenly to all pods which are part of this service.

4. SInce we are using minikube , it doesnt show a external IP , as it is limited . WE will get external IP once we deploy the cluster in the cloud , BUt still if we want to reach the application there is a special command , which will give access to this service by basically mapping a port to the IP , which we can reach from our local machine.

minikube service <deployment-name>  - this is minikube specific command .

Restarting containers : 


1. If we hit the error route of the application making the container delabirtely to fail , it will crash the container in the pod , and thus it will try to restart the container in the pod and bring back the application. This is feature of auto-healing in kubernetes.