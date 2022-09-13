- ***Liveness Probe:*** indicates if the container is operating. If so, no action is taken. If not, the kubelet kills and restarts the container. Learn more in our guide to Kubernetes liveness probes.
- ***Readiness Probe:*** indicates whether the application running in the container is ready to accept requests. If so, Services matching the pod are allowed to send traffic to it. If not, the endpoints controller removes the pod from all matching Kubernetes Services.
- ***Startup Probe:*** indicates whether the application running in the container has started. If so, other probes start functioning. If not, the kubelet kills and restarts the container.

### how to check the logging information?
- kubectl logs podname -c containername
- login to control plane server, check the folder /var/log/containers/ for all log of all containers.
- login to Control Plane server, check the folder var/log/containers/kube-apiserver-k8s-control_kube-system_kube-apiserver-
- login to Control Plane server, check the log for Kubelet: "sudo journalctl -u kubelet" (because Kubelet is running as a service)
