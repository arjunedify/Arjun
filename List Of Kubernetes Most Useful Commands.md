![](RackMultipart20230517-1-48wxp9_html_38ac99f1f0d34c9.png)

**ListOfKubernetesMostUsefulCommands**

1.
# Pods

$kubectlgetpods

$kubectlgetpods—all-namespaces

$kubectlgetpodmonkey-owide

$kubectlgetpodmonkey-oyaml

$kubectldescribepodmonkey

1.
# CreateDeployments

_ **Create** __**single**__ **deployment:** _

$kubectlrunmonkey—image=monkey—record

1.
# ScalingPODs

$kubectlscaledeployment/POD\_NAME—replicas=N

1.
# PODUpgradeandhistoryListhistoryofdeployments:

$kubectlrollouthistorydeployment/DEPLOYMENT\_NAME

# Jumptospecificrevision:

$kubectlrolloutundodeployment/DEPLOYMENT\_NAME—to-revision=N

1.
# Services

_ **List** __ **services:** _

$kubectlgetservices

# ExposePODsasservices(createsendpoints)

$kubectlexposedeployment/monkey—port=2001—

type=NodePort

1.
# Volumes

_ **List** __**Persistent**__ **Volumes** __**and**__ **Persistent** __**Volumes**__ **Claims:** _

$kubectlgetpv

$kubectlgetpvc

1.
# Secrets

_ **List** __**Persistent**__ **Volumes** __**and**__ **Persistent** __**Volumes**__ **Claims:** _

$kubectlgetsecrets

$kubectlcreatesecretgeneric—help

$kubectlcreatesecretgenericmysql—from-literal=password=root

$kubectlgetsecretsmysql-oyaml

1.
# ConfigMaps

_ **List** __**Persistent**__ **Volumes** __**and**__ **Persistent** __**Volumes**__ **Claims:** _

$kubectlcreateconfigmapfoobar—from-file=config.js

$kubectlgetconfigmapfoobar-oyaml

1.
# DNS

_ **List** __ **DNS-PODs:** _

$kubectlgetpods—all-namespaces|grepdns

# CheckDNSforpodnginx(assumingabusyboxPOD/containerisrunning)

$kubectlexec-tibusybox—nslookupnginx

**Note:** kube-proxyrunningintheworkernodesmanageservicesandsetiptablesrulestodirecttraffic.

1.
# Ingress

_ **List** __ **DNS-PODs:** _

$kubectlgetingress

$kubectlexposedeploymentghost—port=2368

1.
# HorizontalPodAutoscalerWhenheapsterruns:

$kubectlgethpa

$kubectlautoscale—help

1.
# DaemonSets

$kubectlgetdaemonsets

$kubectlgetds

1.
# SchedulerNodeSelectorbasedpolicy:

$kubectllabelnodeminikubefoo=bar

# NodeBindingthroughAPIServer:

$kubectlproxy

$ curl -H "Content-Type: application/json" -X POST — data@binding.json http://localhost:8001/api/v1/namespaces/default/pods/foobar-sched/binding

1.
# TaintsandTolerations

_ **NodeSelector** __**based**__ **policy:** _

$kubectltaintnodemasterfoo=bar:NoSchedule

1.
# Troubleshooting

$kubectldescribe

$kubectllogs

$kubectlexec

$kubectlgetnodes—show-labels

$kubectlgetevents

1.
# RoleBasedAccessControl

$kubectlcreaterolefluent-reader—verb=get—verb=list—

verb=watch—resource=pods

$kubectlcreaterolebindingfoo—role=fluent-reader—

user=minikube

$kubectlgetrolebindingfoo-oyaml
