   
 
   1 kubectl apply -f cm.yaml
   2 kubectl get cm
   3 kubectl describe configmap cm-example
   4 kubectl apply  -f pod.yaml
   5 kubectl exec mybox -it -- /bin/sh
   6 kubectl exec mybox -it -- /bin/sh | echo $CITY
   
  7 kubectl delete -f cm.yaml
  8 kubectl delete -f pod.yaml