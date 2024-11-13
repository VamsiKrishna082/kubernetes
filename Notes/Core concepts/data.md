1. THis page is about data and volumes.

2. HOw to persist data the containers generating and so on.

3. State is data created and used by your application which must not be lost

there are two types of data:

user-generated data , user accounts , ofter stored in databases , but could also be files.

intermediate results derived by the app , often stored in memory , temperory database tables or files

Inorder to data to survive container restarts we need volumes to persist the data.

volumes -> kubernetes runs our containers - > kubernetes needs to be configured to add volumes to our containers.

kubernetes can mount volumes into containers
1. a broad variety of volume types / drivers are supported (local volumes i.e on nodes ), cloud provider specific volumes.

2. volume lifetime depends on the pod lifetime , volume survives container restarts and removal , volumes are removed when pods are destroyed.


kubernetes volumes - supports many different drivers and types , volumes are not necessarly persistant , volumes survive container restarts and removals but doesnt survive pod restarts.

docker volumes - Basically no driver/ type support , volumes persist until manually cleared , volumes survive container restarts and removals , here there is no concept of pods.


three major types of volume:

1. emptyDir
2. csi
3. hostPath

emptyDir: basic volume.It simply creates a directory inside the pod , which is mapped to a container internal directory inside of the container. Data survives container restarts but not pod restarts.

it has a downtime.

what if we have two replicas of the pod , if one of our container in one pod goes down , the traffic might reach other pod for which it will still give the data not found error since the emptyDir would have stored data in other pod.


hostPath: This allows us to set up a path on the node/host machine , then the data will be exposed to multiple pods.

emptyDir is one dir per pod , hostpath is common dir on host machine shared to all the pods.
with hostpath we cannot solve the problem if we have multiple hostmachines/node, but with minikube which is a single node machine , it will solve for now.

hostpath is similar to kind of bindmount.

csi - container storage interface.

csi provides a great integration to many drivers allowed in the market , one of which is efs , which can be great use.

there is a concept called persistant volumes. They will be pod and node independent.

This concept of persistant volumes is much bigger than pod and node independece, the volume is completely removed from pod lifecycle and is managed by the cluster. We can define the volume and it can be claimed by any pod , this makes us to reduce the times we add the changes related to volumes in our deployment yaml files

persistant volumes are resources present inside the cluster / somewhere in cloud like any other service..we create a persistant volument claim in a pod , and we claim the volume in the pod.

we can have claims to multiple different persistant volumes





