Task 3

Creating the 2-stage Dockerfile to run the Java application

First clone the Java source code on your VM git clone https://github.com/Iftequar7/JavaWeb.git

![](RackMultipart20230518-1-jw4s5p_html_1ba2aa985001591d.png)

Now enter into the JavaWeb directory then ls to check the source code

![](RackMultipart20230518-1-jw4s5p_html_f0a43d276a78b122.png)

Now write the 2-stage Dockerfile vi Dockerfile

![](RackMultipart20230518-1-jw4s5p_html_b33a0f4d3e80e79.png)

Then build the docker image by using docker build -t \<any\_name\> .

The process would looks like this

![](RackMultipart20230518-1-jw4s5p_html_6cfe8ff246e0a767.png)

![](RackMultipart20230518-1-jw4s5p_html_baecfb501bf484cf.png)

Check the image by docker images

![](RackMultipart20230518-1-jw4s5p_html_24a3a9ac893248cd.png)

Now create the container & run it on port 8081 instead of 8080 with this command docker run -dt -p 8081:8080 \<image\_name\>

![](RackMultipart20230518-1-jw4s5p_html_e8516da47ad9019f.png)

Check the docker container by docker ps

![](RackMultipart20230518-1-jw4s5p_html_c2cbc0a14b58f82f.png)

Mention this port number on your Security Group of your Instance

![](RackMultipart20230518-1-jw4s5p_html_cbdea5f2364c5567.png)

Now brows the application in your browser with \<ip\_address:8081 /WebAppCal-0.0.6\>

The output would be this

![](RackMultipart20230518-1-jw4s5p_html_879535a8fde04437.png)
