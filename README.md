## Kubertenes(k8s) exercice

Learning kubernetes and its cli tool `kubectl`. Running a small web application with a MongoDB database
The Goal was sync one MongoDB pod with the Webapp pod in a local Kubernetes cluster.
Accessing the Local IP address and the port for the Web application

### Dependencies
- Docker as container engine
- Kubernetes as orchestration tool
- Minikube for running a local Kubernetes cluster

### Running the examples
- First start the local cluster and wait until the cluster is ready
  `$ minikube start `
- In the `k8s-demo` folder there are `.yaml` files for running the different K8s components
- Load those config files using Kubectl one by one(there should be a better method, I'm a newby)
  `$ kubectl apply -f ./k8s-demo/mongo-config.yaml`
  `$ kubectl apply -f ./k8s-demo/mongo-secret.yaml`
  `$ kubectl apply -f ./k8s-demo/mongo-deployment.yaml`
  `$ kubectl apply -f ./k8s-demo/mongo-service.yaml`
  `$ kubectl apply -f ./k8s-demo/webapp-deployment.yaml`
  `$ kubectl apply -f ./k8s-demo/webapp-service.yaml`
- Check the statuses for the pods, all of them should be "Running"
  `$ kubectl get pods -o wide`
- Get the local IP address from Minikube cluster(LOCAL IP column output)
  `$ kubectl get node -o wide`
- Get the Webapp PORT exposed(PORT(S) column)
  `$ kubectl get svc -o wide `
- With those values (IP address and port) go to the browser y type them
- You should see the website
- Profit!

Did you kow Kubernetes is a Greek word, meaning “helmsman” or “pilot.”?


