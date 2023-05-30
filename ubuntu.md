# **Installations**

- Like the control panel in windows, we have **dpkg** and **apt** commands to perform installations.
- **dpkg (Debian package)** in Linux is the primary package manager for Debian and Debian-based systems, such as **Ubuntu**.
- The tool installs, builds, removes, configures, and retrieves information for Debian packages. The command works with packages in .deb format.
- dpkg -l
- dpkg -l | wc -l

dpkg - Debian package

l - list

| - pipe { join commands }

wc -l - word count, specify lines

- dpkg -l | grep -w zip
- dpkg -l | grep -w java
- dpkg -l | grep -w python3
- dpkg -l | grep -w unzip
- unzip

- Download file using curl
  - curl http://some.url --output some.file
  - curl http://ftp.de.debian.org/debian/pool/main/z/zip/zip\_3.0-11+b1\_amd64.deb --output zip.deb

- Install deb file
  - sudo dpkg -i [.deb file]
  - dpkg -l | grep -w zip
  - zip
  - sudo dpkg -i zip.deb
  - dpkg -l | grep -w zip
  - zip

- Download file using curl
  - curl http://ftp.de.debian.org/debian/pool/main/e/elinks/elinks\_0.13~20190125-3\_arm64.deb --output elinks.deb

- Install / Upgrade deb file
  - sudo dpkg -i [.deb file]
  - dpkg -l | grep -w elinks
  - elinks
  - sudo dpkg -i elinks.deb

![](RackMultipart20230530-1-yh2xxz_html_5040a4e8595f904.png)

  - dpkg -l | grep -w elinks
  - elinks

# **Erase**

Uninstall the application

\> sudo dpkg -r package\_name

\> dpkg -r $(dpkg -f your-file-here.deb Package)

# **DEB Cons**

- Manually download deb files and install
- Manually do the updates
- Manually manage the dependencies

- The above cons can be overcome with **"**** apt ****" package manager**.

- To overcome the above problems and make the installation process easy, industry came up with a functionality called **repository**.

# **What is a Package Repository ?**

A software repository, or " **repo**" for short, is a storage location for software packages.It is a collection of all related files, w.r.t given OS version

# **APT**

\> **Yum :: Yellowdog Updater, Modified**

\> sudo apt update

\> sudo apt list --installed

\> sudo apt list --installed | grep \<package\>

\> sudo apt list --installed | grep java

\> sudo apt list --installed | grep python3

Install & Update

\> sudo apt -y install \<package\>

\> sudo apt -y install elinks

Remove

\> sudo apt -y remove \<package\>

\> sudo apt -y remove elinks

![](RackMultipart20230530-1-yh2xxz_html_ef74e9ec14c83084.png)

\> sudo apt-get install -y mongodb-org

\> No package mongodb-org available.

[https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/)

By default we have some basic repositories for our use in **/etc/apt/sources.list.d/**

But to use them:

\> We need internet

\> We Need to identify which package we need

# **Advantages of repo**

\> No need to manually download

\> No Dependency Management

\> It fails over to nearest repo automatically

Repos info is stored in **/etc/apt/sources.list.d/**

We have **.list** files in /etc/apt/sources.list.d/, these are files which contain links towards the actual repo.

[https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/](https://www.mongodb.com/docs/manual/tutorial/install-mongodb-on-ubuntu/)

# **Binary Installation - KOPS**

\> curl -Lo kops https://github.com/kubernetes/kops/releases/download/$(curl -s https://api.github.com/repos/kubernetes/kops/releases/latest | grep tag\_name | cut -d '"' -f 4)/kops-linux-amd64

\> chmod +x kops

\> sudo mv kops /usr/local/bin/kops
