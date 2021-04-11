# Learning the Kubernetes 

Deploying Application to Kubernetes:
$ kubectl create deployment --image <image name> <deployment name>
  eg: $ kubectl create deployment --image nginxdemos/hello myweb
  
Scaling the existing deployment 
$ kubectl scale deployment --replicas 10 myweb

Exposing the deployment to the network
$ kubectl expose deployment myweb --port=80 --type=LoadBalancer

Check the service
$ kubectl get service

Deleting the deployment and serviec
$ kubectl delete service myweb
$ kubectl delete deployment myweb



Deploying application with kubernetes manifest YAML file.
Get a) ngnix-deployment.yaml and b) nginix-service.yaml files from https://gitlab.com/nanuchi/youtube-tutorial-series/-/tree/master/kubernetes-configuration-file-explained

$ kubectl apply -f nginix-deployment.yaml
$ kubectl apply -f nginix-service.yaml
$ kubectl get service 
$ kubectl describe service nginix-service    <<  Check endpoints
$ kubectl get pod -o wide   << Check the IP of pods
$ kubectl get deployment nginix-deployment -o yaml   << Get the running yaml of the deployment. It has the stats part.

