1. Most important service / server which is running on master run is api-server.

2. This is the counterpart for kubelet , to communicate to worker nodes.

3. Other important part is scheduler , Watches for new pods , selects worker nodes to run them on.

4. we got kube-controller manager , watches and controls worker nodes , correct no of pods , and more.

5. we got cloud controller manager , it is specific for particular cloud , it is like kube controller manager but it knows how to interact with cloud provider resources.

6. services is a term in kubernetes world , to make sure pod is reacheable to outside world.