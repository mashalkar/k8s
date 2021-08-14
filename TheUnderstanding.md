Kubernetes: 
Kubernetes is an open-source container-orchestration system for automating and monitoring deployment, scaling, and managing containerized applications.

Architecture: 
A working Kubernetes deployment is called a cluster. Kubernetes cluster has two parts: the master/control plane and the compute/worker nodes.
- The control plane's components make global decisions about the cluster (for example, scheduling), as well as detecting and responding to cluster events. 
  It manages the worker nodes and the Pods in the cluster.
- The worker node is Physical or Virtual machine where application container pods are deployed.
  
There are different services running on both Control plane and worker nodes. 
 - Control Plane: 
   - Kube-APIServer, which acts as the frontend to the cluster. All internal and external communication to the cluster is via the API-Server. 
     The users, management devices, and command line interfaces all talk to this API server to interact with the Kubernetes cluster.
     It is designed to scale horizontally. 
   - Kube-Controller-Manager, which runs a set of controllers for the running cluster. The controller-manager implements governance across the cluster.
     List of controllers:
      - Node Controller: Responsible for noticing and responding when nodes go down.
      - Replication Controller: Responsible for maintaining the correct number of pods for every replication controller object in the system.
      - Endpoints Controller: Populates the Endpoints object (that is, it joins Services and Pods).
      - Service Account and Token Controllers: Create default accounts and API access tokens for new namespaces.
      - Cloud-Controller-Manager: runs controllers that interact with the underlying cloud providers. 
   - Etcd, the cluster state database. It is Consistent and highly-available key-value store used as Kubernetes' backing store for all cluster data. 
   - Kube Scheduler, which schedules activities to the worker nodes based on events occurring on the etcd. 
     It also holds the nodes resources plan to determine the proper action for the triggered event. 
     It watches for newly created Pods with no assigned node, and selects a node for them to run on.
     Factors taken into account for scheduling decisions include: individual and collective resource requirements, hardware/software/policy constraints, 
     affinity and anti-affinity specifications, data locality, inter-workload interference, and deadlines.

 - Worker Node:
   - Kubelet: An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod.
     The kubelet takes a set of PodSpecs that are provided through various mechanisms and ensures that the containers described in those PodSpecs are running and healthy. 
     The kubelet doesn't manage containers which were not created by Kubernetes.
   - Kube-proxy: kube-proxy is a network proxy that runs on each node in your cluster, implementing part of the Kubernetes Service concept.
     It maintains network rules on nodes. These network rules allow network communication to your Pods from network sessions inside or outside of your cluster.
     It uses the operating system packet filtering layer if there is one and it's available. Otherwise, kube-proxy forwards the traffic itself.
   - Container runtime: The container runtime is the software that is responsible for running containers.
     Kubernetes supports several container runtimes: Docker, containerd, CRI-O, and any implementation of the Kubernetes CRI (Container Runtime Interface).




# Resources
[Kube in nutshell](https://www.bmc.com/blogs/what-is-kubernetes/)\
