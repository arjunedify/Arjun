**Load balancer**

**How to Create Load balancer:**

- Create 2 instances with diff availability zones.
- For ex: I have launched 2 food websites using Httpd (port: 80)
- Then open Gitbash to so that we can add apache httpd server to the instance.
- We can use below commands to set up httpd and clone from git.

- Sudo yum -y install httpd
- Sudo systemctl start httpd
- Sudo systemctl enable httpd
- To check whether httpd working or not use: sudo systemctl status httpd
- Sudo yum -y install git
- sudo git clone [https://github.com/ravi2krishna/food.git](https://github.com/ravi2krishna/food.git) (from git rep) /var/www/html (document root)
- now to the website to see the final result.

- Now create another instance, so that we can create a load balancer.

![Shape1](RackMultipart20230518-1-885rhr_html_efed1a73e3991140.gif) ![](RackMultipart20230518-1-885rhr_html_894cad84ee6d0f72.png)

![Shape2](RackMultipart20230518-1-885rhr_html_efed1a73e3991140.gif) ![](RackMultipart20230518-1-885rhr_html_6ac9b4e1deb025b4.png)

**Load balancer:**

- In EC2 page find an option LOAD BALANCERS.
- Click on create load balancer.
- Click on classic load balancer – create.
- Give load balancer name (ex: foodsiteof2)
- Ensure that port is http (80).
- Click on assign security group
- Create a new security group or we can add an existing http also.
- Security group name (ex: foodsite-lp-sg)
- Configure health check
- Monitor few important items like Response timeout, unhealthy threshold, health threshold.
- Add instance, select required instances.
- Add tags
- A common DNS will be created for both the sites.

![](RackMultipart20230518-1-885rhr_html_594a3976ba8ad8d1.png)

![](RackMultipart20230518-1-885rhr_html_cdf4bca3e2426f1a.png)
