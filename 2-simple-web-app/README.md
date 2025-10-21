# About this exercise
Learn: Deployments, Pods, and Services.
Do: Deploy an NGINX web server or a simple HTML app container. Expose it via a ClusterIP Service, then upgrade to a NodePort Service to access it externally.
Output: Access your app in a browser using your node’s IP and confirmed access through Kubernetes Service routing.

# Preparing Docker Image for the deployment:
- Added the needed files for a simple webpage in /web directory
- Then the webpage is dockerized using the Dockerfile
`docker build -t hithesh24/simple-web-app:latest .`
- The built image is pushed to docker hub
`docker push hithesh24/simple-web-app:latest`
- The image pushed to docker hub is used in the Kubernetes deployment

# Deployment and Services
- A deployment file is created which has the plan to create the pods like the metadata (app-name), number of replicas, what image to use, etc.
- A service (NodePort) is created to expose the port used by the pod (port 80) to a port (called NodePort) on the host machine so that we can access it from outside the cluster
- Both of these configurations are used to create the pods and to expose the service outside the cluster