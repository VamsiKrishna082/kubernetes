use kubectl logs <pod-name> to see detail logs if container crashes

If there are multiple containers in one pod , we can communicate to other pod via localhost:port.

If we want to do pod to pod communication we need to expose services on each pods , then we can communicate based on the service IP Address , we can get the IP by kubectl get services , and refer to required service fetch the IP and hardcode it in the code.

this is not best practice , other way is to use kubernetes built in environment variables , whenever a service is created in a cluster , kubernetes by default has a environment variable
<SERVICE_NAME_SERVICE_HOST> where all caps and hyphens replaced by underscores.

ANother way of communication is by using core DNS , kubernetes by default has coreDNS Enabled so we can communicate to the other service/ other pod by referencing <service-name.namespaceName>

ex: auth-service.default , where default is the namespace.