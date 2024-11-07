Why Kubernetes/Architecture of kubernetes?

Problems in using AWS ECS and why we need to move towards kubernetes: 

1. THe problems mentioned was easily acheivable and solvable through AWS ECS , like ecs does container health checks + automatic re-deployment , autoscaling and loadbalancing as well. This was the main reasons why we moved towards managed services like ecs , than deploying and running containers on ec2 instances.

2. But we have one disadvantage of using aws ecs.

3. Using a specific cloud service locks us in only using that service only.

4. For defining the configurations of aws ecs , we would have writted pre-defined config files for ecs , which when in future if we try to move to another service by another cloud provider , it makes us difficult to re-write the config files based on that service for that particular cloud provider , so using ecs locks us only using that particular service alone because the settings defined is aws specific only.

5. You need to learn about the specifics, services and config options of another provider if you want to switch to a new cloud provider , and we need to re-write the configuration written.

6. THis might be totally fine if we are going to use only AWS, but can be a issue if we move to a different cloud provider. This is where kubernetes can help us.


What is kubernetes exactly?

1. kubernetes is a open source system for containier orchestration.

2. it can help us for automatic deployment , scaling , loadbalancing and management of our containerized applications.

3. Write down a kubernetes configuration , like what image to be used , how many containers , networking everything in a config file independent of the cloud provider , pass the config using specific tools -> then to any cloud provider and help us creating the required containers.

4. kubernetes configuration : standardized way of describing the to be created and to be managed resources of the kubernetes cluster.

5. kubernetes is a collection of concepts and tools, open source project.

6. kubernetes works alongside with docker. and it is not a paid service , it is a free open source project. You might need to pay , if we use a managed kubernetes specific cloud service like aws eks.

7. you can think kubernetes is like docker compose for multiple machines.

Kubernetes architecture

1. pod is smallest possible unit

2. Pod can hold and run containers, even one or more containers can be run in a single pod.

3. now with the pod with the container inside it itself runs on a so called worker node.

4. worker nodes are simply a machine / vm or ec2 instances

5. we can have more than one pod running inside a single worker node.

6. inside the worker node there is another thing called proxy/config which kubernetes sets up for us , which helps to control the network traffic.

7. So basically to control whether these pods can reach the internet and how these pods and therefore the containers running inside of them, can be reached from the outside world.

8. WHen working with kubernetes , we atleast need one worker node, otherwise theere is no place to run pods.

9. FOr bigger applications , we might have multiple worker nodes , which are then able to run different pods. bECause you might want to have more than one server to match the compute power.

10. Based on traffic in/out you might want pods to scale in/out , distribute traffic equally on all worker nodes , now these worker nodes needs to be controlled somehow , such that someone needs to create and start the containers and pods running on them ,someone needs to shutdown the pods/container if they are failing, this is the work done by master nodes.

11. So master node is the control plane , which talks to the worker node and schedules the pods , scales pods , monitor pods and manages the worker nodes.

12. So as a developer you just develop the end state , i.e how many containers you need to start with , scaling other stuff and u leave it with kubernetes to handle the rest . So , we dont directly talk to worker nodes , control plane or master nodes does that job.

13. In the end master node is yet another server / vm which has control plane running on it.

14. We can also have one machine which has master and worker nodes running on it . BUt for prod systems , it is recommened to have master node seperately and worker nodes seperately.

15. ALl together ( worker and master nodes) together forms a cluster.

16. Master nodes sends instructions to cloud provider api to tell cloud provider to creates the specific resources.
