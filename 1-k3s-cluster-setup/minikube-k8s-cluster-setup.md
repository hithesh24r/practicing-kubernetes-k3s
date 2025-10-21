# Setting up a local kubernetes cluster using minikube
- When we dont have multiple machines or nodes to setup k3s, we can use minikube to setup a multi node setup using docker containers (or other drivers)

- To start a minikube server using docker as the driver:
```minikube start \
    --nodes 3 \
    --driver=docker
    --memory 8192mb \
    --cpus 4
    -p my-minikube-cluster```

- To check the state of the cluster and the status of the nodes
`kubectl get nodes -o wide`
`kubectl get nodes`

- To stop the minikube cluster
`minikube stop -p my-k3s-cluster`

- To delete the minikube cluster
`minikube delete -p my-k3s-cluster`

- To delete all the minikube clusters on the machine
`minikube delete --all`