# Kubernetes
___
## Info
### Master node components
**API server**
- Handles cluster *operations*, *configuration*, *communication*
**Controller manager**
- Ensures desired state of cluster by *monitoring* and *reconciling* actual state with the expected state
**Scheduler**
- Assigns newly created Pods to worker nodes based on *resource requirements*, *policies* and *constraints*
- Ensures optimal distribution of workload across the cluster
**etcd** (distributed key-value store)
- Maintains the *configuration* and *state* of the entire cluster
- Serves as the authoritative source of truth, storing *critical information* about cluster components and their current status
### Worker Nodes
- Assigned own private IP-Address
___
## Cluster Setup
### 1. Worker Nodes
1. Add container runtime (e.g. Docker)
2. Install Kubernetes (Kube-Proxy, Kubelet)
### 2. Setup Communication with Control Plane/Master Node
1. Install Kubectl (on local device)
2. `chmod +x ./kubectl` Make executable
3. `sudo mv .kubectl /usr/local/bin/kubectl` Move to PATH
4. Create `kubeconfig.yaml`
	1. *Configure Server Address*: Set the server address in your `kubeconfig.yaml`
	- `kubectl config set-cluster my-cluster --server=https://api-server-address`
	2. *Configure Authentication*: Set up authentication for kubectl in the `kubeconfig.yaml`
	- `kubectl config set-credentials my-user --token=your-token`
	3. *Set Context*: Combine the cluster and user configs into a context in the `kubeconfig.yaml`
	- `kubectl config set-context my-context --cluster=my-cluster --user=my-user`
	4. *Use Context*: Switch to context to set current cluster, user, namespace in `kubeconfig.yaml`
	- `kubectl config use-context my-context`
5. `export KUBECONFIG=kubeconfig.yaml` Set env variable `KUBECONFIG` to `kubeconfig.yaml`
### 3. Distribution
**Create Container manually**
- `kube ctl run <name> --image=<image> --port=80`

**Create Containers with detailed manifest**
1. Create `application/deployment.yaml` [Syntax](https://kubernetes.io/docs/concepts/overview/working-with-objects/#describing-a-kubernetes-object)
2. `kubectl apply -f <application_deployment.yaml>`
### 4. Expose Network App running as Pods with Load balancer
**Create Service** (Load balancer)
1. Create `application_service.yaml` [Syntax](https://kubernetes.io/docs/concepts/services-networking/service/#loadbalancer)
2. `kubectl apply -f <application_service.yaml>`
*Note*: `targetPort` (`service.yaml`) == `containerPort` (`manifest.yaml`) make sure they match

