1. Make use of minikube which is a single node kubernetes cluster , can be used for development purposes.

2. We have kubermatic tool , AWS EKS are some managed tools for kubernetes.

3. Inorder for kubernetes to run , we need to setup the cluster manually , so that our kubernetes will manage our pods , scaling , monitoring , ensured accessed and reached , keep ur app up and running and so on.

4. EIther we need to setup all resources manually like master node and worker node and configure each services like api server kubelet kube proxt everything , or else we can use managed services like kubermatc , AWS EKS , GKE , openshift which will provide us the infrastructure on which kubernetes can be run on.

5. For local setup of cluster , we can make use of tool like minikube.

kubectl

1. A tool for sending instructions to the K8 cluster

2. wITh help of kubectl , we send instructions to the master node , which then further sends instructions to the worker node, for ex if we want to increase no of pods , with the help of kubectl we send info to the master node.