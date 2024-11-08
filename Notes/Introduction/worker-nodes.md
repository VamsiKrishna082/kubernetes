1. WOrker node is a machine / ec2 instance.

2. Worker node is controlled by master node.

3. Worker node contains more than one pods.

4. POds can hold more than one container , volumes .

5. Pods are managed by kubernetes i.e through master node.

6. Worker node also consists of docker , which is required because pod which holds containers requires docker to spin up containers.

7. ALso consists of kublet which is responsible for communication between worker and master nodes.

8. also consists of kube-proxy which is responsible for incoming and outgoing network traffic from a node to pod , pod -pod communications and to outside world too.

