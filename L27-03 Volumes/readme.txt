   1 kubectl apply -f pv.yaml
   2 kubectl get pv
   3 kubectl apply -f pvc.yaml
   4 kubectl get pv
   5 kubectl get pvc
   6 kubectl apply -f pod.yaml
   7 kubectl exec mybox -it -- /bin/sh
   8 cd demo  cat > hello.txt Hello World!  exit
   9 clear
  10 kubectl delete  -f pod.yaml --force --grace-period=0
  11 kubectl apply -f pod.yaml
  12 kubectl exec mybox -it -- /bin/sh
  13 kubectl delete -f pod.yaml
  14 kubectl delete -f pv.yaml
  15 kubectl delete -f pvc.yaml
 