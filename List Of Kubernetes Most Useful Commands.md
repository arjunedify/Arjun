![](RackMultipart20230517-1-48wxp9_html_38ac99f1f0d34c9.png)

**ListOfKubernetesMostUsefulCommands**

1.
# Pods
```
kubectl get pods
```
```
kubectl get pods —all-namespaces
```
```
 kubectl get podmonkey -o wide
```
```
 kubectl get podmonkey -o yaml
```
```
 kubectl describe pod monkey
```
1.
# CreateDeployments

_ **Create** __**single**__ **deployment:** _
```
kubectl run monkey —image=monkey —record
```
1.
# ScalingPODs
```
kubectl scale deployment/POD-NAME —replicas=N
```
1.
# PODUpgradeandhistoryListhistoryofdeployments:
```
kubectl rollout history deployment/DEPLOYMENT-NAME
```
# Jumptospecificrevision:
```
kubectl rollout undo deployment/DEPLOYMENT-NAME —to-revision=N
```
1.
# Services

_ **List** __ **services:** _
```
kubectl get services
```
# ExposePODsasservices(createsendpoints)
```
kubectl expose deployment/monkey —port=2001 —type=NodePort
```
1.
# Volumes

_ **List** __**Persistent**__ **Volumes** __**and**__ **Persistent** __**Volumes**__ **Claims:** _
```
kubectl get pv
```
```
kubectl get pvc
```
1.
# Secrets

_ **List** __**Persistent**__ **Volumes** __**and**__ **Persistent** __**Volumes**__ **Claims:** _
```
kubectl get secrets
```
```
kubectl create secret generic —help
```
```
kubectl create secret generic mysql --from-literal=password=root
```
```
kubectl get secrets mysql -o yaml
```
1.
# ConfigMaps

_ **List** __**Persistent**__ **Volumes** __**and**__ **Persistent** __**Volumes**__ **Claims:** _
```
kubectl create configmap foobar --from-file=config.js
```
```
kubectl get configmap foobar-oyaml
```
1.
# DNS

_ **List** __ **DNS-PODs:** _
```
kubectl get pods --all-namespaces | grep dns
```
# CheckDNSforpodnginx(assumingabusyboxPOD/containerisrunning)
```
kubectl exec -ti busybox—nslookupnginx
```
**Note:** kube-proxyrunningintheworkernodesmanageservicesandsetiptablesrulestodirecttraffic.

1.
# Ingress

_ **List** __ **DNS-PODs:** _
```
kubectl get ingress
```
```
kubectl expose deployment g host—port=2368
```
1.
# HorizontalPodAutoscalerWhenheapsterruns:
```
kubectl get hpa
```
```
kubectl autoscale —help
```
1.
# DaemonSets
```
kubectl get daemonsets
```
```
kubectlget ds
```
1.
# SchedulerNodeSelectorbasedpolicy:
```
kubectl label node minikube foo=bar
```
# NodeBindingthroughAPIServer:

kubectl proxy

curl -H "Content-Type: application/json" -X POST — data@binding.json http://localhost:8001/api/v1/namespaces/default/pods/foobar-sched/binding


# TaintsandTolerations

_ **NodeSelector** __**based**__ **policy:** _
```
kubectl taint node master foo=bar:NoSchedule
```

# Troubleshooting
```
kubectl describe
```
```
kubectl logs
```
```
kubectl exec
```
```
kubectl get nodes —show-labels
```
```
kubectl get events
```
1.
# RoleBasedAccessControl
```
kubectl create role fluent-reader --verb=get,list,watch --resource=pods
```
kubectl create rolebinding foo --role=fluent-reader --user=minikube
```

```
kubectl get rolebinding foo -o yaml
```
