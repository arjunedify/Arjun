1. Kubernetes cluster setup with KOPS

Note we can create cluster with KOPS(everything manages by us)

and EKS(pass service)(master will be managed by aws)

1. Install aws cli in workstation

1. Install kubectl tool on workstation

1.
2. ![](RackMultipart20230513-1-ho09gz_html_67ed2e90956a0225.png)

1. Kops installation
2. ![](RackMultipart20230513-1-ho09gz_html_475f18f381f9a6c6.png)

1. ![](RackMultipart20230513-1-ho09gz_html_bc2ebcca1ee5026e.png)

1. Create a buket in S3
2. ![](RackMultipart20230513-1-ho09gz_html_69bab1313974f4fa.png)

1. After creating buckets expose the bucket using expose command
2. ![](RackMultipart20230513-1-ho09gz_html_1987f6822d1b47b.png)

Now create a cluster with kops$ kops create cluster --state=s3://kubernetestestbucket --zones=us-east-1a,us-east-1b --node-count=2 --name=test.k8s.local

1. ![](RackMultipart20230513-1-ho09gz_html_b7b341b68d5c811a.png)

1. Now press Up arrow - - yes
2. Now run - - yes - - admin command as shown in below
3. ![](RackMultipart20230513-1-ho09gz_html_393770804dfad679.png)

1. kops validate cluster --wait 10m to ping and check status

1. to check nodes after creation of cluster

1. ![](RackMultipart20230513-1-ho09gz_html_7e4f13b118c21e4f.png)

1. **$cat .kube/config**

**Copy from api version to ……**

**Save this in notepad this file is used for authentication**


