## Service Types:
- CusterIP: Service exposes the applicationn within the cluster network where it can be accessed by other pPods
- NodePort: Service exposes the application externally by listening on an exteranl port on each cluster node. 
## Ingress - a Kubernetes object
- An Ingress is a Kubernetes object that manages access to Services feom outside the cluster
- NodePort can be leveraged to expose applications externally, but Ingress can provide external access to applications with some more powerful features that something like a NodePort doesn't have. 
- Normally Ingress is used in the context of cloud platform like AWS or Microsoft Azure. And they basically manage external access by automatically configuring things within that cloud platform to manage that external access. They can also provide additional features like SSL termination, or you can even code your own Ingress controllers to basically do anything you want. 
- It's worth to note that you do need the Ingress controller to actually implemetn the Ingress functionality. Without Ingress Controller, you can create Ingress objects, but they actually don't do anything.  

## Some use cases of Kubernetes Ingress include:
- Providing externally reachable URLs for services
- Load balancing traffic
- Offering name-based virtual hosting
- Terminating SSL or TLS

## Kubernetes Ingress consists of two core coponents:
- ***Ingress API object:*** The API object indicates the services that need to be exposed outside the cluster. It consitss of the routing rules.
- ***Ingress Controller:*** Ingress Controller is the actual implementation of Ingress. It is usually a load balancer that routes traffic from the API to the desired services within the Kubernetes cluster.
