# Contents

[**1. What are the different types of services offered in the cloud?** 1](#_Toc55574871)

[**2. What is cloud computing?** 1](#_Toc55574872)

[**3. What are the different cloud deployment models?** 1](#_Toc55574873)

[**4. I have some private servers on my premises, also I have distributed some of my workload on the public cloud, what is this architecture called?** 2](#_Toc55574874)

[**Section 2: Basic Azure Questions** 2](#_Toc55574875)

[**5. What is Microsoft Azure and why is it used?** 2](#_Toc55574876)

[**6. Which service in Azure is used to manage resources in Azure?** 2](#_Toc55574877)

[**7. Which of the following web applications can be deployed with Azure?** 2](#_Toc55574878)

[**Section 3: Azure Interview Questions** 3](#_Toc55574879)

[**8. What are Roles and why do we use them?** 3](#_Toc55574880)

[**9. A \_\_\_\_\_\_\_\_\_ role is a virtual machine instance running Microsoft IIS Web server that can accept and respond to HTTP or HTTPS requests.** 3](#_Toc55574881)

[**10. Is it possible to create a Virtual Machine using Azure Resource Manager in a Virtual Network that was created using classic deployment?** 4](#_Toc55574882)

[**11. What are virtual machine scale sets in Azure?** 4](#_Toc55574883)

[**12. Are data disks supported within scale sets?** 4](#_Toc55574884)

[**13. What is an Availability Set?** 4](#_Toc55574885)

[**14. What are Fault Domains?** 5](#_Toc55574886)

[**15. What are Update Domains?** 5](#_Toc55574887)

[**16. What are Network Security Groups?** 5](#_Toc55574888)

[**17. Do scale sets work with Azure availability sets?** 5](#_Toc55574889)

[**18. What is a break-fix issue?** 6](#_Toc55574890)

[**19. Why is Azure Active Directory used?** 6](#_Toc55574891)

[**20. What happens when you exhaust the maximum failed attempts for authenticating yourself via Azure AD?** 6](#_Toc55574892)

[**21. Where can I find a list of applications that are pre-integrated with Azure AD and their capabilities?** 6](#_Toc55574893)

[**22. How can I use applications with Azure AD that I'm using on-premises?** 6](#_Toc55574894)

[**23. What is Azure Service Fabric?** 6](#_Toc55574895)

[**24. What is a VNet?** 7](#_Toc55574896)

[**25. What are the differences between Subscription Administrator and Directory Administrator?** 7](#_Toc55574897)

[**26. Are there any scale limitations for customers using managed disks?** 7](#_Toc55574898)

[**27. What is the difference between Service Bus Queues and Storage Queues?** 7](#_Toc55574899)

[**28. What is Azure Redis Cache?** 8](#_Toc55574900)

[**29. Why doesn't Azure Redis Cache have an MSDN class library reference like some of the other Azure services?** 8](#_Toc55574901)

[**30. What are Redis databases?** 9](#_Toc55574902)

[**31. Is it possible to add an existing VM to an availability set?** 9](#_Toc55574903)

[**32. What are the username requirements when creating a VM?** 9](#_Toc55574904)

[**33. What are the password requirements when creating a VM?** 9](#_Toc55574905)

[**34. How much storage can I use with a virtual machine?** 10](#_Toc55574906)

[**35. How can one create a Virtual Machine in Powershell?** 10](#_Toc55574907)

[**36. How to create a Network Security Group and a Network Security Group Rule?** 10](#_Toc55574908)

[**37. How to create a new storage account and container using Power Shell?** 11](#_Toc55574909)

[**38. How can one create a VM in Azure CLI?** 11](#_Toc55574910)

[**39. What are the various power states of a VM?** 12](#_Toc55574911)

[**40. How can you retrieve the state of a particular VM?** 12](#_Toc55574912)

[**41. How can you stop a VM using Power Shell?** 12](#_Toc55574913)

[**42. Why was my client disconnected from the cache?** 12](#_Toc55574914)

[**43. What is Azure Search?** 13](#_Toc55574915)

[**44. My web app still uses an old Docker container image after I've updated the image on Docker Hub. Does Azure support continuous integration/deployment of custom containers?** 13](#_Toc55574916)

[**45. What are the expected values for the Startup File section when I configure the runtime stack?** 13](#_Toc55574917)

[**46. How are Azure Marketplace subscriptions priced?** 13](#_Toc55574918)

[**47. What is the difference between "price," "software price," and "total price" in the cost structure for Virtual Machine offers in the Azure Marketplace?** 14](#_Toc55574919)

[**48. What are stateful and stateless microservices for Service Fabric?** 14](#_Toc55574920)

[**49. What is the meaning of application partitions?** 15](#_Toc55574921)

[**50. What are special Azure Regions?** 15](#_Toc55574922)

### Why Did You Choose a Career in Cloud Computing?

These types of Azure interview questions require a thoughtful, honest response. By thinking through your answer ahead of time, you'll be ready to say something your interviewer will approve of. Show that you care about the field and that you have a passion for cloud computing and the problems it can solve.

### Why Did You Choose Microsoft Azure and Not Aws?

Your response to this question is based on your own background and experience. Maybe you come from a developer background, so Azure appealed to you. Maybe your first cloud computing role just happened to be with Azure. As with the question above, the key here is to be ready to give an intelligent answer to the question.

**How Does Microsoft Azure Compare to Aws?**

This might be a matter of opinion for you, so answer as you see fit. In general, people say Azure is a better choice because it's a Microsoft product, making it easier for organizations already using Windows Server, SQL Server, and Exchange to move to the cloud. In addition, because of Microsoft's deep knowledge of developer tools, Azure offers multiple app deployment options for developers, which makes it stand out against AWS.

### How Did You Learn Azure?

Did you learn Azure through a certification? Through on-the-job experience? A little of each? However you learned it, make sure to demonstrate to the interviewer that you have practical experience (if you're new to the field) and that you are continuing to learn.

### Tell Me About a Problem You Solved at Your Prior Job.

This is something to spend some time on when you're preparing responses to possible Azure interview questions. As a cloud architect, you need to show that you are a good listener and problem solver, as well as a good communicator. Yes, you need to know the technology, but cloud computing does not usually involve sitting isolated in a cubicle. You'll have stakeholders to listen to, problems to solve, and options to present. When you answer questions like these, try to convey that you are a team player and a good communicator, in addition to being a really good Azure architect.

**1.What are the different types of services offered in the cloud?**

| **IAAS VS PAAS VS SAAS** |
| --- |
| **IAAS** | **PAAS** | **SAAS** |
| In infrastructure as a service, you get the raw hardware from your cloud provider as a service i.e you get a server which you can configure with your own will. | Platform as a Service, gives you a platform to publish without giving the access to the underlying software or OS.  | You get software as a service in Azure, i.e no infrastructure, no platform, simple software that you can use without purchasing it. |
| For Example: Azure VM, Amazon EC2. | For example: Web Apps, Mobile Apps in Azure. | For example: when you launch a VM on Azure, you are not buying the OS, you are basically renting it for the time you will be running that instance. |

**2. What is cloud computing?**

**Explanation:**  It is the use of servers on the internet to "store", "manage" and "process" data. The difference is, instead of using your own servers, you are using someone else's servers to do your task, paying them for the amount of time you use it for.

**3. What are the different cloud deployment models?**

**Explanation:**  Following are the three cloud deployment models:

**Public Cloud:**  The infrastructure is owned by your cloud provider and the server that you are using could be a multi-tenant system.

**Private Cloud: ** The infrastructure is owned by you or your cloud provider gives you that service exclusively. For eg: Hosting your website on your servers, or hosting your website with the cloud provider on a dedicated server.

**Hybrid Cloud: ** When you use both Public Cloud, Private Cloud together, it is called Hybrid Cloud. For Example: Using your in-house servers for confidential data, and the public cloud for hosting your company's public facing website. This type of setup would be a hybrid cloud.

**4. I have some private servers on my premises, also I have distributed some of my workload on the public cloud, what is this architecture called?**

1. Virtual Private Network
2. Private Cloud
3. Virtual Private Cloud
4. Hybrid Cloud

**Answer: D. Hybrid Cloud**

**Explanation: ** This type of architecture would be a hybrid cloud. Why? Because we are using both, the public cloud, and on premises servers i.e the private cloud. To make this hybrid architecture easy to use, wouldn't it be better if your private and public cloud were all on the same network (virtually). This is established by including your public cloud servers in a virtual private cloud, and connecting virtual cloud with your on-premise servers using a VPN (Virtual Private Network).

**Section 2: Basic Azure Questions**

**5. What is Microsoft Azure and why is it used?**

**Explanation: ** As discussed above, the companies which provide the cloud service are called the Cloud Providers. There are a lot of cloud providers out there, out of them one is Microsoft Azure. It is used for accessing Microsoft's infrastructure for cloud.

**6. Which service in Azure is used to manage resources in Azure?**

1. Application Insights
2. Azure Resource Manager
3. Azure Portal
4. Log Analytics

**Answer: B Azure Resource Manager**

**Explanation: ** Azure Resource Manager is used to "manage" infrastructures which involve a no. of azure services. It can be used to deploy, manage and delete all the resources together using a simple JSON script.

**7. Which of the following web applications can be deployed with Azure?**

1. ASP.NET
2. PHP
3. WCF
4. All of the mentioned

**Answer: D All of the mentioned**

**Explanation: ** Microsoft also has released SDKs for both Java and Ruby to allow applications written in those languages to place calls to the Azure Service Platform API to the AppFabric Service.

**Section 3: Azure Interview Questions**

**8. What are Roles and why do we use them?**

**Explanation: ** Roles are nothing servers in layman terms. These servers are managed, load balanced, Platform as a Service virtual machines that work together to achieve a common goal.

There are 3 types of roles in Microsoft Azure:

- Web Role
- Worker Role
- VM  Role

Let's discuss each of these roles in detail:

- **Web Role –**  A web role is basically used to deploy a website, using languages supported by the IIS platform like, PHP, .NET etc. It is configured and customized to run web applications.
- **Worker Role – ** A worker role is more like an help to the Web role, it used to execute background processes unlike the Web Role which is used to deploy the website.
- **VM Role – ** The VM role is used by a user to schedule tasks and other windows services. This role can be used to customize the machines on which the web and worker role is running.

**9. A \_\_\_\_\_\_\_\_\_ role is a virtual machine instance running Microsoft IIS Web server that can accept and respond to HTTP or HTTPS requests.**

1. Web
2. Server
3. Worker
4. Client

**Answer: A. Web **

**Explanation: ** The answer should be Web Roles, there are no roles such as Server or Client roles. Also, Worker roles can only communicate with Azure Storage or through direct connections to clients.

**10. Is it possible to create a Virtual Machine using Azure Resource Manager in a Virtual Network that was created using classic deployment?**

**Explanation: ** This is not supported. You cannot use Azure Resource Manager to deploy a virtual machine into a virtual network that was created using classic deployment.

**11. What are virtual machine scale sets in Azure?**

**Explanation: ** Virtual machine scale sets are Azure compute resource that you can use to deploy and manage a set of identical VMs. With all the VMs configured the same, scale sets are designed to support true autoscale, and no pre-provisioning of VMs is required. So it's easier to build large-scale services that target big compute, big data, and containerized workloads.

**12. Are data disks supported within scale sets?**

**Explanation: ** Yes. A scale set can define an attached data disk configuration that applies to all VMs in the set. Other options for storing data include:

- Azure files (SMB shared drives)
- OS drive
- Temp drive (local, not backed by Azure Storage)
- Azure data service (for example, Azure tables, Azure blobs)
- External data service (for example, remote database)

**13. What is an Availability Set?**

**Explanation:**  An availability set is a logical grouping of VMs that allows Azure to understand how your application is built to provide redundancy and availability. It is recommended that two or more VMs are created within an availability set to provide for a highly available application and to meet the 99.95% Azure SLA. When a single VM is used with Azure Premium Storage, the Azure SLA applies for unplanned maintenance events.

**14. What are Fault Domains?**

**Explanation:**  A fault domain is a logical group of underlying hardware that share a common power source and network switch, similar to a rack within an on-premise data-centers. As you create VMs within an availability set, the Azure platform automatically distributes your VMs across these fault domains. This approach limits the impact of potential physical hardware failures, network outages, or power interruptions.

**15. What are Update Domains?**

**Explanation:**  An update domain is a logical group of underlying hardware that can undergo maintenance or can be rebooted at the same time. As you create VMs within an availability set, the Azure platform automatically distributes your VMs across these update domains. This approach ensures that at least one instance of your application always remains running as the Azure platform undergoes periodic maintenance. The order of update domains being rebooted may not proceed sequentially during planned maintenance, but only one update domain is rebooted at a time.

**16. What are Network Security Groups?**

**Explanation: ** A network security group (NSG) contains a list of Access Control List (ACL) rules that allow or deny network traffic to subnets, NICs, or both. NSGs can be associated with either subnets or individual NICs connected to a subnet. When an NSG is associated with a subnet, the ACL rules apply to all the VMs in that subnet. In addition, traffic to an individual NIC can be restricted by associating an NSG directly to a NIC.

**17. Do scale sets work with Azure availability sets?**

**Explanation: ** Yes. A scale set is an implicit availability set with 5 fault domains and 5 update domains. Scale sets of more than 100 VMs span multiple _placement groups_, which are equivalent to multiple availability sets. An availability set of VMs can exist in the same virtual network as a scale set of VMs. A common configuration is to put control node VMs (which often require unique configuration) in an availability set and put data nodes in the scale set.

**18. What is a break-fix issue?**

**Explanation: ** Technical problems are called break-fix issue, it is an industry term which refers to "work involved in supporting a technology when it fails in the normal course of its function, which requires intervention by a support organization to be restored to working order".

**19. Why is Azure Active Directory used?**

**Explanation: ** Azure Active Directory is an Identity and Access Management system. It is used to grant access to your employees to specific products and services in your network. For example: Salesforce.com, twitter etc. Azure AD has some in-built support for applications in its gallery which can be added directly.

**20. What happens when you exhaust the maximum failed attempts for authenticating yourself via Azure AD?**

**Explanation: ** We use a more sophisticated strategy to lock accounts. This is based on the IP address of the request and the passwords entered. The duration of the lockout also increases based on the likelihood that it is an attack.

**21. Where can I find a list of applications that are pre-integrated with Azure AD and their capabilities?**

**Explanation: ** Azure AD has around 2600 pre-integrated applications. All pre-integrated applications support single sign-on (SSO). SSO let you use your organizational credentials to access your apps. Some of the applications also support automated provisioning and de-provisioning.

**22. How can I use applications with Azure AD that I'm using on-premises?**

**Explanation: ** Azure AD gives you an easy and secure way to connect to the web applications you choose. You can access these applications in the same way you access your SaaS apps in Azure AD, no need for a VPN to change your network infrastructure.

**23. What is Azure Service Fabric?**

**Explanation: ** Azure Service Fabric is a distributed systems platform that makes it easy to package, deploy, and manage scalable and reliable micro-services. Service Fabric also addresses the significant challenges in developing and managing cloud applications. Developers and administrators can avoid complex infrastructure problems and focus on implementing mission-critical, demanding workloads that are scalable, reliable, and manageable. Service Fabric represents the next-generation middleware platform for building and managing these enterprise-class, tier-1, cloud-scale applications.

**24. What is a VNet?**

**Explanation: ** VNet is a representation of your own network in the cloud. It logically isolates your instances launched in the cloud, from the rest of your resources.

**25. What are the differences between Subscription Administrator and Directory Administrator?**

**Explanation: ** By default, one is assigned the Subscription Administrator role when he/she signs up for Azure. A subscription admin can use either a Microsoft account or a work or school account from the directory that the Azure subscription is associated with. This role is authorized to manage services in the Azure portal. If others need to sign in and access services by using the same subscription, you can add them as co-admins.

Azure AD has a different set of admin roles to manage the directory and identity-related features. These admins will have access to various features in the Azure portal or the Azure classic portal. The admin's role determines what they can do, like create or edit users, assign administrative roles to others, reset user passwords, manage user licenses, or manage domains.

**26. Are there any scale limitations for customers using managed disks?**

**Explanation:**  Managed Disks eliminates the limits associated with storage accounts. However, the number of managed disks per subscription is limited to 2000 by default.

**27. What is the difference between Service Bus Queues and Storage Queues?**

**Explanation: ** The Azure Storage Queue is simple and the developer experience is quite good. It uses the local Azure Storage Emulator and debugging is made quite easy. The tooling for Azure Storage Queues allows you to easily peek at the top 32 messages and if the messages are in XML or Json, you're able to visualize their contents directly from Visual Studio Furthermore, these queues can be purged of their contents, which is especially useful during development and QA efforts.

The Azure Service Bus Queues are evolved and surrounded by many useful mechanisms that make it enterprise worthy! They are built into the Service Bus and are able to forward messages to other Queues and Topics. They have a built-in dead-letter queue and messages have a time to live that you control, hence messages don't automatically disappear after 7 days.

Furthermore, Azure Service Bus Queues have the ability of deleting themselves after a configurable amount of idle time. This feature is very practical when you create Queues for each user, because if a user hasn't interacted with a Queue for the past month, it automatically gets clean it up. Its also a great way to drive costs down. You shouldn't have to pay for storage that you don't need. These Queues are limited to a maximum of 80gb. Once you've reached this limit your application will start receiving exceptions.

**28. What is Azure Redis Cache?**

**Redis**  is an open source (BSD licensed), in-memory data structure store, used as a database,  **cache**  and message broker. Azure Redis Cache is based on the popular open-source Redis cache. It gives you access to a secure, dedicated Redis cache, managed by Microsoft, and accessible from any application within Azure.  It supports data structures such as strings, hashes, lists, sets, sorted sets with range queries, bitmaps, hyperloglogs and geospatial indexes with radius queries.

**29. Why doesn't Azure Redis Cache have an MSDN class library reference like some of the other Azure services?**

**Explanation: ** Microsoft Azure Redis Cache is based on the popular open source Redis Cache and can be accessed by a wide variety of Redis clients for many programming languages. Each client has its own API that makes calls to the Redis cache instance using Redis commands.

Because each client is different, there is not one centralized class reference on MSDN, and each client maintains its own reference documentation. In addition to the reference documentation, there are several tutorials showing how to get started with Azure Redis Cache using different languages and cache clients. To access these tutorials, see How to use Azure Redis Cache and click the desired language from the language switcher at the top of the article.

**30. What are Redis databases?**

**Explanation: ** Redis Databases are just a logical separation of data within the same Redis instance. The cache memory is shared between all the databases and actual memory consumption of a given database depends on the keys/values stored in that database. For example, a C6 cache has 53 GB of memory. You can choose to put all 53 GB into one database or you can split it up between multiple databases.

**31. Is it possible to add an existing VM to an availability set?**

**Explanation:**  No. If you want your VM to be part of an availability set, you need to create the VM within the set. There currently no way to add a VM to an availability set after it has been created.

**32. What are the username requirements when creating a VM?**

**Explanation:**  Usernames can be a maximum of 20 characters in length and cannot end in a period (".").

The following usernames are not allowed:

![](RackMultipart20230518-1-ad0b24_html_6713e8454651eba9.png)

**33. What are the password requirements when creating a VM?**

**Explanation:**  Passwords must be 12 – 123 characters in length and meet 3 out of the following 4 complexity requirements:

- Have lower characters
- Have upper characters
- Have a digit
- Have a special character (Regex match [W\_])

The following passwords are not allowed:

![Shape1](RackMultipart20230518-1-ad0b24_html_6ba668124285aec4.gif)

**34. How much storage can I use with a virtual machine?**

**Explanation: ** Each data disk can be up to 1 TB. The number of data disks which you can use depends on the size of the virtual machine.

Azure Managed Disks are the new and recommended disk storage offerings for use with Azure Virtual Machines for persistent storage of data. You can use multiple Managed Disks with each Virtual Machine. Managed Disks offer two types of durable storage options: Premium and Standard Managed Disks.

Azure storage accounts can also provide storage for the operating system disk and any data disks. Each disk is a .vhd file stored as a page blob.

**35. How can one create a Virtual Machine in Powershell?**

# Define a credential object

$cred = Get-Credential

# Create a virtual machine configuration

$vmConfig = New-AzureRmVMConfig -VMName myVM -VMSize Standard\_DS2 |

` Set-AzureRmVMOperatingSystem -Windows -ComputerName myVM -Credential $cred |

` Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer `

-Skus 2016-Datacenter -Version latest | Add-AzureRmVMNetworkInterface -Id $nic.Id

**36. How to create a Network Security Group and a Network Security Group Rule?**

# Create an inbound network security group rule for port 3389

$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP -Protocol Tcp `

-Direction Inbound -Priority 1000 -SourceAddressPrefix \* -SourcePortRange \* -DestinationAddressPrefix \* `

-DestinationPortRange 3389 -Access Allow

# Create an inbound network security group rule for port 80

$nsgRuleWeb = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleWWW -Protocol Tcp `

-Direction Inbound -Priority 1001 -SourceAddressPrefix \* -SourcePortRange \* -DestinationAddressPrefix \* `

-DestinationPortRange 80 -Access Allow

# Create a network security group

$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName myResourceGroup -Location EastUS `

-Name myNetworkSecurityGroup -SecurityRules $nsgRuleRDP,$nsgRuleWeb

**37. How to create a new storage account and container using Power Shell?**

$storageName = "st" + (Get-Random)

New-AzureRmStorageAccount -ResourceGroupName "myResourceGroup" -AccountName $storageName -Location "West US" -SkuName "Standard\_LRS" -Kind Storage

$accountKey = (Get-AzureRmStorageAccountKey -ResourceGroupName myResourceGroup -Name $storageName).Value[0]

$context = New-AzureStorageContext -StorageAccountName $storageName -StorageAccountKey $accountKey

New-AzureStorageContainer -Name "templates" -Context $context -Permission Container

**38. How can one create a VM in Azure CLI?**

az vm create ` --resource-group myResourceGroup ` --name myVM --image win2016datacenter ` --admin-username azureuser ` --admin-password myPassword12

**39. What are the various power states of a VM?**![](RackMultipart20230518-1-ad0b24_html_e18921367b8eef35.png)

**40. How can you retrieve the state of a particular VM?**

Get-AzureRmVM `

-ResourceGroupName myResourceGroup `

-Name myVM `

-Status | Select @{n="Status"; e={$\_.Statuses[1].Code}}

**41. How can you stop a VM using Power Shell?**

Stop-AzureRmVM -ResourceGroupName myResourceGroupVM -Name "myVM" -Force

**42. Why was my client disconnected from the cache?**

**Explanation: ** The following are some common reason for a cache disconnect.

- Client-side causes
  - The client application was redeployed.
  - The client application performed a scaling operation.
  - In the case of Cloud Services or Web Apps, this may be due to auto-scaling.
  - The networking layer on the client side changed.
  - Transient errors occurred in the client or in the network nodes between the client and the server.
  - The bandwidth threshold limits were reached.
  - CPU bound operations took too long to complete.
- Server-side causes
  - On the standard cache offering, the Azure Redis Cache service initiated a fail-over from the primary node to the secondary node.
  - Azure was patching the instance where the cache was deployed
  - This can be for Redis server updates or general VM maintenance.

**43. What is Azure Search?**

**Explanation: ** Azure Search is a cloud search-as-a-service solution that delegates server and infrastructure management to Microsoft, leaving you with a ready-to-use service that you can populate with your data and then use to add search to your web or mobile application. Azure Search allows you to easily add a robust search experience to your applications using a simple REST API or .NET SDK without managing search infrastructure or becoming an expert in search.

**44. My web app still uses an old Docker container image after I've updated the image on Docker Hub. Does Azure support continuous integration/deployment of custom containers?**

**Explanation: ** Yes, it does. For private registries, you can update the container by stopping and then re-starting your web app. Alternatively, you can also change or add a dummy application setting to force an update of your container.

**45. What are the expected values for the Startup File section when I configure the runtime stack?**

**Explanation: ** For Node.Js, you specify the PM2 configuration file or your script file. For .NET Core, specify your compiled DLL name. For Ruby, you can specify the Ruby script that you want to initialize your app with.

**46. How are Azure Marketplace subscriptions priced?**

**Explanation:**

Pricing will vary based on product types. ISV software charges and Azure infrastructure costs are charged separately through your Azure subscription. Pricing models include:

**BYOL Model:**  Bring-your-own-license. You obtain outside of the Azure Marketplace, the right to access or use the offering and are not charged Azure Marketplace fees for use of the offering in the Azure Marketplace.

**Free: ** Free SKU. Customers are not charged Azure Marketplace fees for use of the offering.

**Free Software Trial:**  Full-featured version of the offer that is promotionally free for a limited period of time. You will not be charged Azure Marketplace fees for use of the offering during a trial period. Upon expiration of the trial period, customers will automatically be charged based on standard rates for use of the offering.

**Usage-Based: ** You are charged or billed based on the extent of your use of the offering. For Virtual Machines Images, you are charged an hourly Azure Marketplace fee. For Data Services, Developer services, and APIs, you are charged per unit of measurement as defined by the offering.

**Monthly Fee: ** You are charged or billed a fixed monthly fee for a subscription to the offering (from the date of subscription start for that particular plan). The monthly fee is not prorated for mid-month cancellations or unused services.

**47. What is the difference between "price," "software price," and "total price" in the cost structure for Virtual Machine offers in the Azure Marketplace?**

**Explanation: **"Price" refers to the cost of the Azure Virtual Machine to run the software. "Software price" refers to the cost of the publisher software running on an Azure Virtual Machine. "Total price" refers to the combined total cost of the Azure Virtual Machine and the publisher software running on an Azure Virtual Machine.

**48. What are stateful and stateless microservices for Service Fabric?**

**Explanation: ** Service Fabric enables you to build applications that consist of microservices. Stateless microservices (such as protocol gateways and web proxies) do not maintain a mutable state outside a request and its response from the service. Azure Cloud Services worker roles are an example of a stateless service. Stateful microservices (such as user accounts, databases, devices, shopping carts, and queues) maintain a mutable, authoritative state beyond the request and its response. Today's Internet-scale applications consist of a combination of stateless and stateful microservices.

**49. What is the meaning of application partitions?**

**Explanation: ** The application partitions are a part of the Active Directory system and having said so, they are directory partitions which are replicated to domain controllers. Usually, domain controllers that are included in the process of directory partitions hold a replica of that directory partition. The attributes and values of application partitions is that you can replicated them to any specific domain controller in a forest, meaning that it could lessen replication traffic. While the domain directory partitions transfer all their data to all of the domains, the application partitions can focus on only one in the domain area. This makes application partitions redundant and more available.

**50. What are special Azure Regions?**

**Explanation: ** Azure has some special regions that you may wish to use when buildingyour applications for compliance or legal purposes. These special regions include:

- **US Gov Virginia**  and  **US Gov Iowa**
  - A physical and logical network-isolated instance of Azure for US government agencies and partners, operated by screened US persons. Includes additional compliance certifications such as [FedRAMP](https://www.microsoft.com/en-us/TrustCenter/Compliance/FedRAMP) and [DISA](https://www.microsoft.com/en-us/TrustCenter/Compliance/DISA).
- **China East**  and  **China North**
  - These regions are available through a unique partnership between Microsoft and 21Vianet, whereby Microsoft does not directly maintain the datacenters.
- **Germany Central**  and  **Germany Northeast**
  - These regions are available via a data trustee model whereby customer data remains in Germany under control of T-Systems, a Deutsche Telekom company, acting as the German data trustee.

**51. What is meant by Microsoft Azure and Azure diagnostic**

**This is one of the most basic Azure cloud interview questions asked very often. Microsoft Azure is a cloud computing interface that is implemented by Microsoft so as to get benefited from the cloud computing.**

**Azure diagnostics is an API based system that collects the data to diagnose the application which is constantly running. It tunes with the verbose monitoring by enabling roles of the cloud services.**

#### 52. What are the main functions of the Azure Cloud Service?

**Answer:**  The main functions of the Azure Cloud Service are;

- It is designed to host the running application and at the same time manage the background running application.
- The application of web processing is termed as "web role" whereas the background processing is termed as the "worker role".
