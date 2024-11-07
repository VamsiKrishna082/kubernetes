Introduction to kubernetes/ Problems faced


1. kubernetes is a open source system for automating deployments , scaling and management of containerized applications.

Problems faced by manual deployment of containers only using docker: 

2. manual deployment of containers is hard to maintain , error-prone and annoying.

3. containers might crash/go down and might need to be replaced.

4. when manually running containers on an EC2 instance, we also have to manually monitor, whenever something crashed, and we have to manually restart containers thereafter. And, it should be needless to say that, that is of course not really something we wanna do for a serious or bigger applications.

5. we might need more container instances upon traffic spikes. Sometimes based on application load , we might need additional instances to run containers on , sometimes we dont need additional instances if the load is less. This scaling up/down is difficult when we try deploying containers on a standalone ec2 instances only using docker.

6. if our application expects incoming traffic , it should be equally distributed with all containers , as we might have multiple instances of same/similar containers running.

