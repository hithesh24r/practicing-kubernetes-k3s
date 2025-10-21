# Simple K3S Cluster Installation
- This Simple cluster will have one master node with any number of worker nodes
- This is ideal for practice purposes or for personal use
- But for a production or any other needs where the availability of the control plane is critical, then we need to configure a Highly Available K3S Cluster with multiple control planes (Master Nodes)

- K3S Install Script - For Master Node
`curl -sfL https://get.k3s.io | sh -`

- K3S Install Script - For Worker Nodes
    - Get the value for K3S_TOKEN from master node at /var/lib/rancher/k3s/server/node-token
`curl -sfL https://get.k3s.io | K3S_URL=https://<MASTER_NODE_IP>:6443 K3S_TOKEN=mynodetoken sh -`

- To check the cluster and nodes' readiness
`kubectl get nodes`