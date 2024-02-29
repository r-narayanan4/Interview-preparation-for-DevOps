# Kubernetes Interview Questions and Answers

## 1. Difference between Docker and Kubernetes

Docker is a container platform used for packaging, distributing, and running applications in containers. It provides a consistent environment for applications to run across different environments.

Kubernetes, on the other hand, is a container orchestration platform that automates the deployment, scaling, and management of containerized applications. It provides features like automatic scaling, load balancing, and self-healing for containerized workloads.

In summary, Docker is primarily focused on building and running containers, while Kubernetes is focused on managing and orchestrating containerized applications.

## 2. What are the main components of a Kubernetes cluster?

Kubernetes clusters consist of several key components:

- **Control Plane Components:**
  - **API Server:** Exposes the Kubernetes API and acts as the front-end for the Kubernetes control plane.
  - **Scheduler:** Assigns nodes to newly created pods based on resource availability and constraints.
  - **Controller Manager:** Monitors the cluster's state and performs cluster management tasks, such as node and pod management.
  - **etcd:** Consistent and highly-available key-value store used to store all Kubernetes cluster data, including configuration and state information.

- **Node Components:**
  - **Kubelet:** Agent running on each node in the cluster, responsible for managing the node and its containers.
  - **Kube-proxy:** Manages network connectivity to Kubernetes services by maintaining network rules and performing connection forwarding.
  - **Container Runtime:** Software responsible for running containers, such as Docker or containerd.

## 3. Difference between Docker Swarm and Kubernetes

Docker Swarm and Kubernetes are both container orchestration platforms, but they have differences in their architecture, features, and ecosystem.

- **Architecture:** Docker Swarm follows a simpler architecture compared to Kubernetes. It is based on Docker Engine and utilizes Swarm mode for clustering. Kubernetes, on the other hand, has a more complex architecture with a master-slave setup, including components like API server, Scheduler, Controller Manager, etcd, etc.
- **Features:** Kubernetes offers more advanced features out-of-the-box, such as auto-scaling, self-healing, rolling updates, and more granular control over container orchestration. Docker Swarm is simpler and easier to set up, suitable for smaller-scale deployments.
- **Ecosystem:** Kubernetes has a larger and more vibrant ecosystem with support from various cloud providers, third-party tools, and a strong community. Docker Swarm has a smaller ecosystem and may have limitations in terms of third-party integrations and support.


## 4. Difference between Docker container and pod

A Docker container is a lightweight, standalone, and executable package that includes everything needed to run a piece of software, including the code, runtime, libraries, and dependencies. It runs directly on the host's operating system kernel and provides process isolation.

In Kubernetes, a pod is the smallest deployable unit and represents a group of one or more containers that are tightly coupled and share resources, such as networking and storage. Pods are scheduled and managed together and can communicate with each other via localhost.

## 5. What is a namespace?

A namespace in Kubernetes is a virtual cluster within a physical cluster. It provides a scope for names, enabling multiple users or teams to share the same physical cluster while maintaining separate resources and access policies. Namespaces are used to organize and segregate resources within a Kubernetes cluster, such as pods, services, and replication controllers.

## 6. What is the role of kube-proxy?

Kube-proxy plays a crucial role in Kubernetes networking. Its main responsibilities include:

- **Service Proxy:** Kube-proxy maintains network rules on each node to enable communication between different pods and services within the Kubernetes cluster. It sets up rules to forward traffic to the appropriate destination pod based on service IP and port.
- **Load Balancing:** Kube-proxy implements load balancing for services with multiple pods by distributing incoming traffic evenly across all healthy pods.
- **Proxy Modes:** Kube-proxy supports different proxy modes, including userspace, iptables, and IPVS modes, to efficiently handle network traffic based on the node's capabilities and requirements.
- **Service Discovery:** Kube-proxy helps in service discovery by providing a stable endpoint for accessing services, even if the underlying pods are dynamically created or terminated.
- **Dynamic Updates:** Kube-proxy dynamically updates network rules as services and pods are added, removed, or modified within the cluster, ensuring continuous connectivity and load balancing.

Kube-proxy is a network proxy that runs on each node in the Kubernetes cluster. Its primary role is to maintain network rules (such as iptables rules) to enable communication to and from the pods from within the cluster and from external clients. Kube-proxy implements services abstraction in Kubernetes, allowing clients to access services using virtual IPs (ClusterIPs), NodePort, or LoadBalancer.


## 7. What are the different types of services within Kubernetes?

Kubernetes supports various types of services to expose applications running in the cluster:

1. **ClusterIP:** Exposes the service on an internal IP within the cluster. This type makes the service accessible only from within the cluster.
2. **NodePort:** Exposes the service on a static port on each node's IP. This makes the service accessible from outside the cluster using `<NodeIP>:<NodePort>`.
3. **LoadBalancer:** Exposes the service externally using a cloud provider's load balancer. This type creates and configures a load balancer in the cloud provider's environment to route traffic to the service.
4. **ExternalName:** Maps a service to a DNS name (specified by the `externalName` field), allowing access to external services by name.

## 8. What is the difference between NodePort and LoadBalancer?

NodePort and LoadBalancer are both ways to expose services externally, but they have different implementations:

- **NodePort:** Exposes the service on a static port on each node's IP address. Clients can access the service using `<NodeIP>:<NodePort>`.
- **LoadBalancer:** Exposes the service using a cloud provider's load balancer. The load balancer routes traffic to the service, providing a single entry point for external access.

## 9. What is the role of kubelet?

Kubelet is the primary node agent that runs on each node in the Kubernetes cluster. Its main responsibilities include:

- Managing the lifecycle of pods, ensuring that they are running and healthy.
- Communicating with the Kubernetes API server to receive pod specifications and report the status of pods.
- Mounting and managing volumes, secrets, and configmaps specified in pod manifests.
- Implementing container runtime interface (CRI) to interact with container runtime (e.g., Docker, containerd) for managing containers.

## 10. What are some day-to-day activities on Kubernetes?

Some common day-to-day activities on Kubernetes include:

- Deploying applications using manifests (e.g., Deployment, StatefulSet, DaemonSet).
- Scaling applications horizontally (adding more replicas) or vertically (resizing pods).
- Updating applications with new versions (rolling updates).
- Monitoring and logging application and cluster metrics.
- Troubleshooting and debugging issues with applications or cluster components.
- Managing access control and RBAC policies.

## 11. What is cgroup?

Control groups (cgroups) is a Linux kernel feature used to limit, account for, and isolate resource usage (CPU, memory, disk I/O, network, etc.) of a collection of processes. Kubernetes uses cgroups to enforce resource limits and isolation for containers running on each node in the cluster.

## 12. Explain some Kubernetes errors?

Common Kubernetes errors include:

- Pod scheduling failures due to resource constraints or affinity/anti-affinity rules.
- Image pull failures when Kubernetes cannot fetch the specified container image.
- Network-related errors such as pod connectivity issues or misconfiguration of network policies.
- Persistent volume (PV) provisioning failures or storage-related issues.
- API server errors due to misconfiguration or unresponsive API endpoints.

## 13. Mention the list of objects of Kubernetes.

| Object               | Description                                                                                           |
|----------------------|-------------------------------------------------------------------------------------------------------|
| Pod                  | The smallest deployable unit in Kubernetes, representing one or more containers and their shared resources. |
| Service              | Defines a set of pods and a policy by which to access them.                                           |
| Volume               | Provides a way for storing data persistently in Kubernetes.                                             |
| Namespace            | Provides a scope for Kubernetes resources, enabling multiple users or teams to share the same cluster. |
| Deployment           | Manages a set of replicated pods with declarative updates and rollback capabilities.                   |
| StatefulSet          | Manages stateful applications by providing guarantees about the ordering and uniqueness of pod creation. |
| DaemonSet            | Ensures that all (or some) nodes run a copy of a pod, useful for running daemons on every node.       |
| ReplicationController | Ensures that a specified number of pod replicas are running at any given time.                          |
| Job                  | Runs a pod to completion, useful for batch or cron jobs.                                                |
| CronJob              | Runs a pod at a specified time or interval, useful for scheduled tasks.                                 |
| Secret               | Stores sensitive data such as passwords, OAuth tokens, or SSH keys.                                     |
| ConfigMap            | Stores configuration data as key-value pairs.                                                          |
| ServiceAccount       | Provides an identity for processes running in a pod.                                                    |
| PersistentVolume     | Represents a piece of storage in the cluster that has been provisioned by an administrator.            |
| PersistentVolumeClaim| Requests storage resources from a PersistentVolume.                                                     |
| Ingress              | Manages external access to services within a cluster, typically for HTTP and HTTPS traffic.             |


## 14. Explain DaemonSets and their uses.

DaemonSets ensure that all (or some) nodes run a copy of a pod. They are useful for running a daemon on every node, such as monitoring agents or log collectors. DaemonSets automatically scale as nodes are added or removed from the cluster.

## 15. Why do we need Container Orchestration in Kubernetes?

Container orchestration in Kubernetes provides several benefits, including:

- Automated deployment and scaling of containerized applications.
- Self-healing capabilities to maintain desired pod replicas.
- Load balancing and service discovery for efficient traffic routing.
- Declarative configuration management using YAML or JSON manifests.
- Resource optimization and efficient utilization of cluster resources.

## 16. Explain StatefulSets in Kubernetes.

StatefulSets are used to manage stateful applications that require stable, unique network identifiers and stable storage. They provide guarantees about the ordering and uniqueness of pod creation, deletion, and scaling. StatefulSets are suitable for databases, distributed systems, and other stateful workloads.

## 17. Explain Replication Controllers.

Replication Controllers ensure that a specified number of pod replicas are running at any given time. They continuously monitor the cluster and create or delete pod replicas as needed to maintain the desired replica count. Replication Controllers are considered a legacy resource in Kubernetes, and Deployments are preferred for managing replica sets.

## 18. Explain the Ingress controller.

An Ingress controller is a Kubernetes resource that manages external access to services within a cluster. It acts as an API gateway for HTTP and HTTPS traffic, routing requests to the appropriate services based on hostname and path rules. Ingress controllers typically integrate with external load balancers or reverse proxies to expose services externally.

## 19. Explain selectors and labels.

Labels are key-value pairs attached to Kubernetes objects, such as pods, services, or deployments, to organize and select subsets of objects. Selectors are used to filter objects based on their labels. They allow users to define rules for selecting objects that match specific criteria, facilitating operations like service discovery, resource allocation, and load balancing.

## 20. Explain node affinity and anti-affinity.

Node affinity and anti-affinity are mechanisms in Kubernetes used to influence pod scheduling decisions based on node labels. Node affinity specifies rules for preferring or requiring pods to be scheduled on nodes with specific labels or node attributes. Node anti-affinity specifies rules for avoiding or disallowing pod scheduling on nodes with specific labels or attributes.


## 21. Explain PV (Persistent Volume) and PVC (Persistent Volume Claim).

- **Persistent Volume (PV):** A Persistent Volume (PV) is a piece of storage in the cluster that has been provisioned by an administrator. It is a resource in the cluster just like a node is a cluster resource. PVs are volume plugins like Volumes but have a lifecycle independent of any individual pod that uses the PV. This lifecycle is controlled by the administrator. PVs can be dynamically provisioned or statically defined.

- **Persistent Volume Claim (PVC):** A Persistent Volume Claim (PVC) is a request for storage by a user. It is similar to a pod. Pods consume node resources and PVCs consume PV resources. Pods can request specific levels of resources (CPU and Memory). Claims can request specific size and access modes (e.g., can be mounted once read/write or many times read-only).

## 22. What is RBAC (Role-Based Access Control)?

Role-Based Access Control (RBAC) is a Kubernetes feature that allows administrators to control access to the Kubernetes API based on roles and permissions. With RBAC, cluster administrators can define roles that specify a set of permissions and then bind those roles to users or groups within the cluster. RBAC enables fine-grained control over who can perform actions within the cluster, such as creating or modifying resources.

## 23. Explain all Kubernetes components and architecture.

The Kubernetes architecture consists of several key components:

- **API Server:** Exposes the Kubernetes API and serves as the frontend for the Kubernetes control plane.
- **Scheduler:** Assigns pods to nodes based on resource availability and user-defined constraints.
- **Controller Manager:** Watches the cluster state and ensures that the desired state matches the actual state.
- **etcd:** Consistent and highly-available key-value store used for storing cluster data, configuration, and state.
- **Kubelet:** Agent running on each node that is responsible for managing the node and its containers.
- **Kube-proxy:** Manages network connectivity and performs connection forwarding for Kubernetes services.
- **Container Runtime:** Software responsible for running containers, such as Docker or containerd.

## 24. What is a sidecar container?

A sidecar container is a secondary container that runs alongside the main application container within the same pod. Sidecar containers extend or enhance the functionality of the main container without altering its core logic. Common uses of sidecar containers include logging, monitoring, or proxying traffic for the main application container.

## 25. What is an init container?

An init container is a specialized container that runs before the main application containers in a pod. Its primary purpose is to perform initialization tasks required by the application, such as setting up configuration files or waiting for a dependent service to be ready. Init containers are executed one at a time, in order, and must successfully complete before the main application containers start.


