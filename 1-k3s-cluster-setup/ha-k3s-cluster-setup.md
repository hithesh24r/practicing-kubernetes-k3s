# Setting up a HA K3S Cluster
- This is for the use cases where the control plane availability is critical
- This cluster will have 3 or more control planes and multiple worker nodes

- Initialixing the cluster with the first master node
`curl -sfL https://get.k3s.io | K3S_TOKEN=SECRET sh -s - server --cluster-init`

- Joining additional master nodes with a shared SECRET
```curl -sfL https://get.k3s.io | K3S_TOKEN=SECRET sh -s - server \
    --server https://<ip or hostname of server1>:6443```

- Joining additional worker nodes to the HA K3S cluster
```curl -sfL https://get.k3s.io | K3S_TOKEN=SECRET sh -s - agent --server https://<ip or hostname of server>:6443```

- To check the cluster and nodes' readiness
`kubectl get nodes`