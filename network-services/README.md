
## Network Policy
- Deployed Network Policies will be only effective if a network plugin is installed in the K8s cluster.
- Intsall a network plugin: https://docs.aws.amazon.com/eks/latest/userguide/calico.html
- EKS cluster doesn't support Network Policy out of the box.
- If a Pod is not selected by any NetworkPolies, the Pod is non-isolated, and all traffic is allowed
- if a Pod is selected by any NetworkPolicy, traffic will be blocked unless it is allowed by at least 1 NetworkPolicy that selects the Pod.
- If you combine a namespaceSelector and podSelector within the same rule, the traffic must meet both the Pod- and Namespace-related conditions in order to be allowed.
- NetworkPolicy is namespaced, means being defined in a specific namespace scope.