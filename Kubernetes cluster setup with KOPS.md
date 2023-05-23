1. Kubernetes cluster setup with KOPS

Note we can create cluster with KOPS(everything manages by us)

and EKS(pass service)(master will be managed by aws)

1. Install aws cli in workstation

1. Install kubectl tool on workstation

1.
2. ![image](https://github.com/arjunedify/Arjun/assets/132984407/17ef3502-d29d-44bc-a584-576aa4e16535)

1. Kops installation
2. ![image](https://github.com/arjunedify/Arjun/assets/132984407/0c9699b4-cb2c-4e49-bfa6-58eb07d75a2f)

1. ![image](https://github.com/arjunedify/Arjun/assets/132984407/29269375-66b7-4a86-8d8e-3ee5ae11e595)

1. Create a buket in S3
2. ![image](https://github.com/arjunedify/Arjun/assets/132984407/49e3b596-369e-4951-b186-1cbd6e515e63)

1. After creating buckets expose the bucket using expose command
2. ![image](https://github.com/arjunedify/Arjun/assets/132984407/3316be18-d119-4e23-ad32-cf700d7868bf)

Now create a cluster with kops$ 
```
kops create cluster --state=s3://kubernetestestbucket --zones=us-east-1a,us-east-1b --node-count=2 --name=test.k8s.local
```
1. ![image](https://github.com/arjunedify/Arjun/assets/132984407/39661e8c-b349-45b0-b922-704df5c823d7)

1. Now press Up arrow - - yes
2. Now run - - yes - - admin command as shown in below
3. ![image](https://github.com/arjunedify/Arjun/assets/132984407/f8602efb-c1e3-4a87-8ad3-d6ffda1a84c9)

1. kops validate cluster --wait 10m to ping and check status

1. to check nodes after creation of cluster

1. ![image](https://github.com/arjunedify/Arjun/assets/132984407/de70d1f8-85c0-4c26-88be-221b2792e39d)
```
cat .kube/config
```

**Copy from api version to ……**

**Save this in notepad this file is used for authentication**


