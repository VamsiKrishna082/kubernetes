1. Make use of minikube which is a single node kubernetes cluster , can be used for development purposes.

2. We have kubermatic tool , AWS EKS are some managed tools for kubernetes.

3. Inorder for kubernetes to run , we need to setup the cluster manually , so that our kubernetes will manage our pods , scaling , monitoring , ensured accessed and reached , keep ur app up and running and so on.

4. EIther we need to setup all resources manually like master node and worker node and configure each services like api server kubelet kube proxt everything , or else we can use managed services like kubermatc , AWS EKS , GKE , openshift which will provide us the infrastructure on which kubernetes can be run on.

5. For local setup of cluster , we can make use of tool like minikube.

kubectl

1. A tool for sending instructions to the K8 cluster

2. wITh help of kubectl , we send instructions to the master node , which then further sends instructions to the worker node, for ex if we want to increase no of pods , with the help of kubectl we send info to the master node.

3. cluster is the technical infrastructure , and kubectl is the communication device for talking to the infrastructure

4. When we give minikube start , this gets created and this again can take a couple of minutes,but now this in the end sets up this virtual machine on your local machine and it creates the Cluster, the Kubernetes Cluster inside of that virtual machine. It creates the master node and installs all the software the master node needs on it. And it also installs all the worker nodes software.
So once this is completed, once this instruction here is done, we have our local development Cluster which we can then control with the kubectl command and where we can then apply our Kubernetes configuration to run our containers inside of this demo local Cluster.

5. use minikube dashboard command to bring up a web dashboard for our cluster.

