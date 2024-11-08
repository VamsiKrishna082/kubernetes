1. kubernetes works with objects.

2. some of the objects are pods , deployment , services , volume and so on...

3. Objects can be created in two different ways , imperative and delarative approach.

4. if you want to create some pod , which then runs a container for u , you need to pass the pod object to the kubernetes cluster either in imperative or declaritive approach , remaining thing kubernetes takes care of.

5. bY default a pod has a clustur internal IP ADdress by default.

6. containers inside a pod can communicate via local host.

7. Pods are designed to be ephermal : kubernetes will start , stop and replace them as needed. for ex : data stored and created in the container is lost  , it is also core idea behind containers , if the contanier run , removed and run again data is lost , it is similar case of pods.

8. pods are tiny wrapper on containers

9. For pods to be managed for you , you need a controller ( eg : deployment object which will create the pods for us ) because we dont only want to create pod , we also want kubernetes to manage the pod for us , create, remove , scale etc and so on..for that a controller ie. deployment object is required to be passed to the cluster.

