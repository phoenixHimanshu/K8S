  
   2 kubectl apply -f secrets.yaml
   3 kubectl get secret
   4 kubectl describe  secret secrets
   5 check username and passwords are printed
   6 kubectl get secret secrets -o yaml
   7 kubectl apply -f pod.yaml
   8 kubectl exec mybox -it  -- /bin/sh
   9 kubectl apply -f pod.yaml
  10 kubectl exec mybox -it  -- /bin/sh
    # echo $USERNAME
    # echo $PASSWORD
  
  