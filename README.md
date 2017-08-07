# grav-poc
Basic grav setup with minikube for demo purposes

Building container:
`docker build -t <you-docker-id>/grav .`
`docker push <you-docker-id>/grav`

* Install minikube following offcial guide: https://kubernetes.io/docs/tasks/tools/install-minikube/
* Start minikube environment with `minikube start`, verify if it's running with `minikube status`
* Ensure your kubectl is pointing to your local cluster with `kubectl get nodes`
* Install helm client and initialise it with `helm init`
* Install Grav application with follwoing command:
`helm install --namespace foo --name bar .`



* Subsequent changes to this deployments can be applied with:
`helm upgrade --install bar . --set image.tag=${BUILD_TAG}`

* Grav page will be served at $(minikube ip):3xxxx (use `kubectl get svc -n foo` to find out port)

* For persistent data Kubernetes offers following solution: https://kubernetes.io/docs/tasks/configure-pod-container/configure-persistent-volume-storage/
