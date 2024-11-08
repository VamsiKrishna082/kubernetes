1. Typically you wont create pod objects and move them to worker node on your own , instead you create deployment objects which u then give info about no of pods , and let kubernetes manage the pods.

2. dEployment object controls multiple pods , you set a desired state and then kubernetes then changes actual state.

3. define which pods and containers to run and the no of instances.

4. wHen creating deployment object , k8 will place the pod on the required worker node which has necessary cpu and memory.

5. If we mess something , we can just rollback the failing deployment .

6. dEployments can be scaled dynamically and automatically.

7. DEployment manage a pod for you , you can also create multiple deployments.

8. ONe kind of a pod eg. a pod with two specific containers . multiple instances of the pod is also possible.

imperative approach to create a deployment :

1. first we need to build the docker image on which we need to run the container.

2. create a object using kubectl create command.

to create a deployment object use : this will create a deployment object and automatically sends to the cluster since which configuring of kubectl , it is configured with minikube.

kubectl create deployment first-app --image=academind/kub-first-app

->  the specified image must be present in dockerhub

kubectl get deployments   -> to see no of deployments running in the cluster.

-> to get further insides , to see no of pods running

kubectl get pods -> we can see the error called imagepullerr , since the specified image is in the local , but it should be present in docker hub.

-> this is because our k8 cluster is in a virtual machine in our machine , and the docker image is in our virtual machine and hence it is not accessed.

-> for now we cannot reach our application from outside world to pod , for that we need to use service object.
