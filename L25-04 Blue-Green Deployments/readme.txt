   // deploy and run Blue enviornment
   1 kubectl create -f hello-dep-v1.yaml
   2 kubectl create -f clusterip.yaml
   3 kubectl get pods -o wide 
  4 kubectl port-forward service/svc-front 8080:8080
  5 check localhost:8080
  //deploy  and run green enviornment now 
  6 kubectl create -f hello-dep-v2.yaml
  7 kubectl get pods -o wide
    # change hello-v1 to hello-v2 for Blue to green deployment (clusterip.yaml)
  8 kubectl apply -f clusterip.yaml
  9 kubectl port-forward service/svc-front 8080:8080
  10 check localhost:8080
  11 clean up
    kubectl delete -f hello-dep-v1.yaml
    kubectl delete -f hello-dep-v2.yaml
    kubectl delete -f clusterip.yaml
