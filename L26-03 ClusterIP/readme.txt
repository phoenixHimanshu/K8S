A service is another type of k8s object
Pod ip's are unreliable but Service ip's are reliable 
Durable ( unlike Pods)
*Static ip address
*Static DNS name
[Servicename].[namespace].svc.cluster.localhost
Services are ways to access pods
Target pods using Selectors
Tree types of services 
i) Cluster ip(Default)
ii) NodePort 
iii) LoadBalancer

Cluster ip
* Cluster ip is the default service
* Visibility 
    Cluster internal 
*port
    The port service is listening to
*TargetPort 
    Redirecting to the port the pod(s) are listening to        
*Load Balanced Round Robin 
    Session affinity is configurable
When to use Cluster ip ???
   1 kubectl apply -f clusterip.yaml
   2 kubectl apply -f deploy-app.yaml
   3 kubectl apply -f pod.yaml
   4 kubectl get pods -o wide
   5 kubectl exec mybox -it -- /bin/sh
        # wget -qO- http://svc-example:8080

  6 kubectl get pods -o wide
  7 kubectl delete -f pod.yaml
  8 kubectl delete -f deploy-app.yaml
  9 kubectl delete -f clusterip.yaml

