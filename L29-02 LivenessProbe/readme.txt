
==================================================================
   - /bin/sh
    - -c
    - touch /tmp/healthy; sleep 15; rm -rf /tmp/healthy; sleep 3600
    is injecting killing event
==================================================================
PS C:\POC\Fundamentals-HandsOn-main\L29-02 LivenessProbe> kubectl apply -f pod.yaml
pod/liveness-example created
PS C:\POC\Fundamentals-HandsOn-main\L29-02 LivenessProbe> kubectl describe pod liveness-example
Name:             liveness-example
Namespace:        default
Priority:         0
Service Account:  default
Node:             minikube/192.168.49.2
Start Time:       Thu, 24 Nov 2022 23:38:32 +0530
Labels:           test=liveness
Annotations:      <none>
Status:           Running
IP:               172.17.0.4
IPs:
  IP:  172.17.0.4
Containers:
  liveness:
    Container ID:  docker://f3bec64674a60d51819df3cfb4f65052aad84d153743ed38af83b27d7919092d
    Image:         busybox
    Image ID:      docker-pullable://busybox@sha256:fcd85228d7a25feb59f101ac3a955d27c80df4ad824d65f5757a954831450185
    Port:          <none>
    Host Port:     <none>
    Args:
      /bin/sh
      -c
      touch /tmp/healthy; sleep 15; rm -rf /tmp/healthy; sleep 3600
    State:          Running
      Started:      Thu, 24 Nov 2022 23:38:37 +0530
    Ready:          True
    Restart Count:  0
    Limits:
      cpu:     250m
      memory:  256Mi
    Requests:
      cpu:        100m
      memory:     128Mi
    Liveness:     exec [cat /tmp/healthy] delay=5s timeout=1s period=5s #success=1 #failure=2
    Environment:  <none>
    Mounts:
      /var/run/secrets/kubernetes.io/serviceaccount from kube-api-access-4mbjg (ro)
Conditions:
  Type              Status
  Initialized       True
  Ready             True
  ContainersReady   True
  PodScheduled      True
Volumes:
  kube-api-access-4mbjg:
    Type:                    Projected (a volume that contains injected data from multiple sources)
    TokenExpirationSeconds:  3607
    ConfigMapName:           kube-root-ca.crt
    ConfigMapOptional:       <nil>
    DownwardAPI:             true
QoS Class:                   Burstable
Node-Selectors:              <none>
Tolerations:                 node.kubernetes.io/not-ready:NoExecute op=Exists for 300s
                             node.kubernetes.io/unreachable:NoExecute op=Exists for 300s
Events:
  Type     Reason     Age                From               Message
  ----     ------     ----               ----               -------
  Normal   Scheduled  56s                default-scheduler  Successfully assigned default/liveness-example to minikube    
  Normal   Pulling    55s                kubelet            Pulling image "busybox"
  Normal   Pulled     52s                kubelet            Successfully pulled image "busybox" in 3.7885063s
  Normal   Created    51s                kubelet            Created container liveness
  Normal   Started    51s                kubelet            Started container liveness
  Warning  Unhealthy  26s (x2 over 31s)  kubelet            Liveness probe failed: cat: can't open '/tmp/healthy': No such file or directory
  Normal   Killing    26s                kubelet            Container liveness failed liveness probe, will be restarted