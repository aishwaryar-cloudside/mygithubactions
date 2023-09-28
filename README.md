# Kubernetes Wordpress installation

## Use minikube to test with
* on macos: 
** brew cask install minikube
** minikube start

## Start the cluster and scale:

* kubectl create secret generic mysql-pass --from-literal=password=YOUR_PASSWORD
* kubectl get secrets
* kubectl create -f mysql-deployment.yaml
* kubectl create -f wordpress-deployment.yaml
* kubectl get pv
* kubectl get pvc
* kubectl get pods
* kubectl get services
* minikube service wordpress --url  (Get URL for wordpress - start install and have fun)

## Scale Wordpress and mysql:

* kubectl scale --replicas X deployments wordpress-mysql
* kubectl scale --replicas X deployments wordpress

## Cleanup

* kubectl delete secret mysql-pass
* kubectl delete deployment -l app=wordpress
* kubectl delete service -l app=wordpress
* kubectl delete pvc -l app=wordpress
* kubectl delete pv -l app=wordpress

## Stop minicube
* minikube stop






