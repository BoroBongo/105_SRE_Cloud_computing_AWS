# SRE DevOps CheatSheet

## Table of Contents

<!-- TOC start -->
- [SRE DevOps CheatSheet](#sre-devops-cheatsheet)
  - [Table of Contents](#table-of-contents)
- [SRE DevOps CheatSheet](#sre-devops-cheatsheet-1)
  - [Table of Contents](#table-of-contents-1)
- [AWS Services](#aws-services)
- [Benefits of Cloud computing](#benefits-of-cloud-computing)
  - [Ease of use](#ease-of-use)
  - [Flexibility](#flexibility)
  - [Robustness](#robustness)
  - [Cost](#cost)
- [What is SRE?](#what-is-sre)
  - [SRE traits](#sre-traits)
  - [AWS Global Infrastructure](#aws-global-infrastructure)
  - [Regions VS Availability Zones](#regions-vs-availability-zones)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing)
    - [Performance](#performance)
    - [Security](#security)
    - [Reliability](#reliability)
    - [Functionality](#functionality)
  - [What is CDN](#what-is-cdn)
  - [What is Auto-Scaling](#what-is-auto-scaling)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud)
    - [On Premises](#on-premises)
    - [Hybrid](#hybrid)
    - [Public Cloud](#public-cloud)
  - [AWS VM connection diagram](#aws-vm-connection-diagram)
  - [Creating of an EC2 Instance](#creating-of-an-ec2-instance)
    - [Linux basics](#linux-basics)
      - [File permissions](#file-permissions)
    - [Bash scripting](#bash-scripting)
  - [Tomcat](#tomcat)
    - [Bash script for tomcat](#bash-script-for-tomcat)
  - [NGINX](#nginx)
  - [Technical interview questions](#technical-interview-questions)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture)
      - [Monolith Architecture](#monolith-architecture)
      - [Microservices Architecture](#microservices-architecture)
    - [2- and N-tier Architecture](#2--and-n-tier-architecture)
      - [2- tier Architecture](#2--tier-architecture)
      - [N-tier Architecture](#n-tier-architecture)
- [Useful links](#useful-links)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski)
      - [AWS Services](#aws-services-1)
- [Benefits of Cloud computing](#benefits-of-cloud-computing-1)
  - [Ease of use](#ease-of-use-1)
  - [Flexibility](#flexibility-1)
  - [Robustness](#robustness-1)
  - [Cost](#cost-1)
  - [What is SRE?](#what-is-sre-1)
    - [SRE traits](#sre-traits-1)
  - [AWS Global Infrastructure](#aws-global-infrastructure-1)
  - [Regions VS Availability Zones](#regions-vs-availability-zones-1)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing-1)
    - [Performance](#performance-1)
    - [Security](#security-1)
    - [Reliability](#reliability-1)
    - [Functionality](#functionality-1)
  - [What is CDN](#what-is-cdn-1)
  - [What is Auto-Scaling](#what-is-auto-scaling-1)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud-1)
    - [On Premises](#on-premises-1)
    - [Hybrid](#hybrid-1)
    - [Public Cloud](#public-cloud-1)
    - [AWS VM connection diagram](#aws-vm-connection-diagram-1)
    - [Creating of an EC2 Instance](#creating-of-an-ec2-instance-1)
  - [___________________](#___________________)
    - [Linux basics](#linux-basics-1)
    - [File permissions](#file-permissions-1)
    - [Bash scripting](#bash-scripting-1)
  - [Tomcat](#tomcat-1)
    - [Bash script for tomcat](#bash-script-for-tomcat-1)
  - [NGINX](#nginx-1)
  - [Technical interview questions](#technical-interview-questions-1)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture-1)
    - [Monolith Architecture](#monolith-architecture-1)
    - [Microservices Architecture](#microservices-architecture-1)
  - [2- and N-tier Architecture](#2--and-n-tier-architecture-1)
    - [2- tier Architecture](#2--tier-architecture-1)
    - [N-tier Architecture](#n-tier-architecture-1)
    - [Useful links](#useful-links-1)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski-1)
- [SRE Intro](#sre-intro)
  - [User Journey](#user-journey)
    - [User experience](#user-experience)
      - [Cloud computing with AWS](#cloud-computing-with-aws)
      - [AWS Services](#aws-services-2)
- [Benefits of Cloud computing](#benefits-of-cloud-computing-2)
  - [Ease of use](#ease-of-use-2)
  - [Flexibility](#flexibility-2)
  - [Robustness](#robustness-2)
  - [Cost](#cost-2)
  - [What is SRE?](#what-is-sre-2)
    - [SRE traits](#sre-traits-2)
  - [AWS Global Infrastructure](#aws-global-infrastructure-2)
  - [Regions VS Availability Zones](#regions-vs-availability-zones-2)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing-2)
    - [Performance](#performance-2)
    - [Security](#security-2)
    - [Reliability](#reliability-2)
    - [Functionality](#functionality-2)
  - [What is CDN](#what-is-cdn-2)
  - [What is Auto-Scaling](#what-is-auto-scaling-2)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud-2)
    - [On Premises](#on-premises-2)
    - [Hybrid](#hybrid-2)
    - [Public Cloud](#public-cloud-2)
    - [AWS VM connection diagram](#aws-vm-connection-diagram-2)
    - [Creating of an EC2 Instance](#creating-of-an-ec2-instance-2)
    - [Linux basics](#linux-basics-2)
    - [File permissions](#file-permissions-2)
    - [Bash scripting](#bash-scripting-2)
  - [Tomcat](#tomcat-2)
    - [Bash script for tomcat](#bash-script-for-tomcat-2)
  - [NGINX](#nginx-2)
  - [Technical interview questions](#technical-interview-questions-2)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture-2)
    - [Monolith Architecture](#monolith-architecture-2)
    - [Microservices Architecture](#microservices-architecture-2)
  - [2- and N-tier Architecture](#2--and-n-tier-architecture-2)
    - [2- tier Architecture](#2--tier-architecture-2)
    - [N-tier Architecture](#n-tier-architecture-2)
    - [Useful links](#useful-links-2)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski-2)
      - [AWS Services](#aws-services-3)
- [Benefits of Cloud computing](#benefits-of-cloud-computing-3)
  - [Ease of use](#ease-of-use-3)
  - [Flexibility](#flexibility-3)
  - [Robustness](#robustness-3)
  - [Cost](#cost-3)
  - [What is SRE?](#what-is-sre-3)
    - [SRE traits](#sre-traits-3)
  - [AWS Global Infrastructure](#aws-global-infrastructure-3)
  - [Regions VS Availability Zones](#regions-vs-availability-zones-3)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing-3)
    - [Performance](#performance-3)
    - [Security](#security-3)
    - [Reliability](#reliability-3)
    - [Functionality](#functionality-3)
  - [What is CDN](#what-is-cdn-3)
  - [What is Auto-Scaling](#what-is-auto-scaling-3)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud-3)
    - [On Premises](#on-premises-3)
    - [Hybrid](#hybrid-3)
    - [Public Cloud](#public-cloud-3)
    - [AWS VM connection diagram](#aws-vm-connection-diagram-3)
    - [Creating of an EC2 Instance](#creating-of-an-ec2-instance-3)
  - [___________________](#___________________-1)
    - [Linux basics](#linux-basics-3)
    - [File permissions](#file-permissions-3)
    - [Bash scripting](#bash-scripting-3)
  - [Tomcat](#tomcat-3)
    - [Bash script for tomcat](#bash-script-for-tomcat-3)
  - [NGINX](#nginx-3)
  - [Technical interview questions](#technical-interview-questions-3)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture-3)
    - [Monolith Architecture](#monolith-architecture-3)
    - [Microservices Architecture](#microservices-architecture-3)
  - [2- and N-tier Architecture](#2--and-n-tier-architecture-3)
    - [2- tier Architecture](#2--tier-architecture-3)
    - [N-tier Architecture](#n-tier-architecture-3)
    - [Useful links](#useful-links-3)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski-3)
- [AWS Services](#aws-services-4)
- [Benefits of Cloud computing](#benefits-of-cloud-computing-4)
  - [Ease of use](#ease-of-use-4)
  - [Flexibility](#flexibility-4)
  - [Robustness](#robustness-4)
  - [Cost](#cost-4)
- [What is SRE?](#what-is-sre-4)
  - [SRE traits](#sre-traits-4)
  - [AWS Global Infrastructure](#aws-global-infrastructure-4)
  - [Regions VS Availability Zones](#regions-vs-availability-zones-4)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing-4)
    - [Performance](#performance-4)
    - [Security](#security-4)
    - [Reliability](#reliability-4)
    - [Functionality](#functionality-4)
  - [What is CDN](#what-is-cdn-4)
  - [What is Auto-Scaling](#what-is-auto-scaling-4)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud-4)
    - [On Premises](#on-premises-4)
    - [Hybrid](#hybrid-4)
    - [Public Cloud](#public-cloud-4)
  - [AWS VM connection diagram](#aws-vm-connection-diagram-4)
  - [Creating of an EC2 Instance](#creating-of-an-ec2-instance-4)
    - [Linux basics](#linux-basics-4)
      - [File permissions](#file-permissions-4)
    - [Bash scripting](#bash-scripting-4)
  - [Tomcat](#tomcat-4)
    - [Bash script for tomcat](#bash-script-for-tomcat-4)
  - [NGINX](#nginx-4)
  - [Technical interview questions](#technical-interview-questions-4)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture-4)
      - [Monolith Architecture](#monolith-architecture-4)
      - [Microservices Architecture](#microservices-architecture-4)
    - [2- and N-tier Architecture](#2--and-n-tier-architecture-4)
      - [2- tier Architecture](#2--tier-architecture-4)
      - [N-tier Architecture](#n-tier-architecture-4)
- [Useful links](#useful-links-4)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski-4)
      - [AWS Services](#aws-services-5)
- [Benefits of Cloud computing](#benefits-of-cloud-computing-5)
  - [Ease of use](#ease-of-use-5)
  - [Flexibility](#flexibility-5)
  - [Robustness](#robustness-5)
  - [Cost](#cost-5)
  - [What is SRE?](#what-is-sre-5)
    - [SRE traits](#sre-traits-5)
  - [AWS Global Infrastructure](#aws-global-infrastructure-5)
  - [Regions VS Availability Zones](#regions-vs-availability-zones-5)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing-5)
    - [Performance](#performance-5)
    - [Security](#security-5)
    - [Reliability](#reliability-5)
    - [Functionality](#functionality-5)
  - [What is CDN](#what-is-cdn-5)
  - [What is Auto-Scaling](#what-is-auto-scaling-5)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud-5)
    - [On Premises](#on-premises-5)
    - [Hybrid](#hybrid-5)
    - [Public Cloud](#public-cloud-5)
    - [AWS VM connection diagram](#aws-vm-connection-diagram-5)
    - [Creating of an EC2 Instance](#creating-of-an-ec2-instance-5)
  - [___________________](#___________________-2)
    - [Linux basics](#linux-basics-5)
    - [File permissions](#file-permissions-5)
    - [Bash scripting](#bash-scripting-5)
  - [Tomcat](#tomcat-5)
    - [Bash script for tomcat](#bash-script-for-tomcat-5)
  - [NGINX](#nginx-5)
  - [Technical interview questions](#technical-interview-questions-5)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture-5)
    - [Monolith Architecture](#monolith-architecture-5)
    - [Microservices Architecture](#microservices-architecture-5)
  - [2- and N-tier Architecture](#2--and-n-tier-architecture-5)
    - [2- tier Architecture](#2--tier-architecture-5)
    - [N-tier Architecture](#n-tier-architecture-5)
    - [Useful links](#useful-links-5)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski-5)
- [SRE Intro](#sre-intro-1)
  - [User Journey](#user-journey-1)
    - [User experience](#user-experience-1)
      - [Cloud computing with AWS](#cloud-computing-with-aws-1)
      - [AWS Services](#aws-services-6)
- [Benefits of Cloud computing](#benefits-of-cloud-computing-6)
  - [Ease of use](#ease-of-use-6)
  - [Flexibility](#flexibility-6)
  - [Robustness](#robustness-6)
  - [Cost](#cost-6)
  - [What is SRE?](#what-is-sre-6)
    - [SRE traits](#sre-traits-6)
  - [AWS Global Infrastructure](#aws-global-infrastructure-6)
  - [Regions VS Availability Zones](#regions-vs-availability-zones-6)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing-6)
    - [Performance](#performance-6)
    - [Security](#security-6)
    - [Reliability](#reliability-6)
    - [Functionality](#functionality-6)
  - [What is CDN](#what-is-cdn-6)
  - [What is Auto-Scaling](#what-is-auto-scaling-6)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud-6)
    - [On Premises](#on-premises-6)
    - [Hybrid](#hybrid-6)
    - [Public Cloud](#public-cloud-6)
    - [AWS VM connection diagram](#aws-vm-connection-diagram-6)
    - [Creating of an EC2 Instance](#creating-of-an-ec2-instance-6)
    - [Linux basics](#linux-basics-6)
    - [File permissions](#file-permissions-6)
    - [Bash scripting](#bash-scripting-6)
  - [Tomcat](#tomcat-6)
    - [Bash script for tomcat](#bash-script-for-tomcat-6)
  - [NGINX](#nginx-6)
  - [Technical interview questions](#technical-interview-questions-6)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture-6)
    - [Monolith Architecture](#monolith-architecture-6)
    - [Microservices Architecture](#microservices-architecture-6)
  - [2- and N-tier Architecture](#2--and-n-tier-architecture-6)
    - [2- tier Architecture](#2--tier-architecture-6)
    - [N-tier Architecture](#n-tier-architecture-6)
    - [Useful links](#useful-links-6)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski-6)
      - [AWS Services](#aws-services-7)
- [Benefits of Cloud computing](#benefits-of-cloud-computing-7)
  - [Ease of use](#ease-of-use-7)
  - [Flexibility](#flexibility-7)
  - [Robustness](#robustness-7)
  - [Cost](#cost-7)
  - [What is SRE?](#what-is-sre-7)
    - [SRE traits](#sre-traits-7)
  - [AWS Global Infrastructure](#aws-global-infrastructure-7)
  - [Regions VS Availability Zones](#regions-vs-availability-zones-7)
  - [Four pillars of cloud computing](#four-pillars-of-cloud-computing-7)
    - [Performance](#performance-7)
    - [Security](#security-7)
    - [Reliability](#reliability-7)
    - [Functionality](#functionality-7)
  - [What is CDN](#what-is-cdn-7)
  - [What is Auto-Scaling](#what-is-auto-scaling-7)
  - [On Prem vs Hybrid vs Public Cloud](#on-prem-vs-hybrid-vs-public-cloud-7)
    - [On Premises](#on-premises-7)
    - [Hybrid](#hybrid-7)
    - [Public Cloud](#public-cloud-7)
    - [AWS VM connection diagram](#aws-vm-connection-diagram-7)
    - [Creating of an EC2 Instance](#creating-of-an-ec2-instance-7)
  - [___________________](#___________________-3)
    - [Linux basics](#linux-basics-7)
    - [File permissions](#file-permissions-7)
    - [Bash scripting](#bash-scripting-7)
  - [Tomcat](#tomcat-7)
    - [Bash script for tomcat](#bash-script-for-tomcat-7)
  - [NGINX](#nginx-7)
  - [Technical interview questions](#technical-interview-questions-7)
  - [Monolith Architecture & Microservices Architecture](#monolith-architecture--microservices-architecture-7)
    - [Monolith Architecture](#monolith-architecture-7)
    - [Microservices Architecture](#microservices-architecture-7)
  - [2- and N-tier Architecture](#2--and-n-tier-architecture-7)
    - [2- tier Architecture](#2--tier-architecture-7)
    - [N-tier Architecture](#n-tier-architecture-7)
    - [Useful links](#useful-links-7)
      - [~Adam Franciszek Felix Kolaczynski](#adam-franciszek-felix-kolaczynski-7)
<!-- TOC end -->
# SRE DevOps CheatSheet

## Table of Contents


# AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

# What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

## SRE traits

- Studious
- Problem Solver
- Creative
- Communicative

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
## AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
## Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
#

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

#### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
#### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

#### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
### 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

#### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

#### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
# Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski

#

#### AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

#

## What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

 ### SRE traits
 - Studious
 - Problem Solver
 - Creative
 - Communicative
 - 

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
### AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
### Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
## ___________________

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
## 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
### Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski


# SRE Intro

## User Journey

### User experience

#### Cloud computing with AWS

#

#### AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

#

## What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

 ### SRE traits
 - Studious
 - Problem Solver
 - Creative
 - Communicative
 - 

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
### AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
### Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
#

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
## 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
### Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski

#

#### AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

#

## What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

 ### SRE traits
 - Studious
 - Problem Solver
 - Creative
 - Communicative
 - 

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
### AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
### Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
## ___________________

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
## 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
### Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski


# AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

# What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

## SRE traits

- Studious
- Problem Solver
- Creative
- Communicative

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
## AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
## Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
#

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

#### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
#### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

#### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
### 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

#### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

#### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
# Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski

#

#### AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

#

## What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

 ### SRE traits
 - Studious
 - Problem Solver
 - Creative
 - Communicative
 - 

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
### AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
### Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
## ___________________

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
## 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
### Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski


# SRE Intro

## User Journey

### User experience

#### Cloud computing with AWS

#

#### AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

#

## What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

 ### SRE traits
 - Studious
 - Problem Solver
 - Creative
 - Communicative
 - 

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
### AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
### Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
#

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
## 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
### Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski

#

#### AWS Services

- Creating github repo to push the markdown doc
- Amazon Web Services (AWS)

# Benefits of Cloud computing

## Ease of use
  
AWS is designed to allow application providers, ISVs, and vendors to quickly and securely host your applications – whether an existing application or a new SaaS-based application.

## Flexibility
  
AWS enables you to select the operating system, programming language, web application platform, database, and other services you need. With AWS, you receive a virtual environment that lets you load the software and services your application requires. This eases the migration process for existing applications while preserving options for building new solutions.

## Robustness
  
With AWS, you take advantage of a scalable, reliable, and secure global computing infrastructure, the virtual backbone of Amazon.com’s multi-billion dollar online business that has been honed for over a decade. Using AWS tools, Auto Scaling, and Elastic Load Balancing, your application can scale up or down based on demand. Backed by Amazon’s massive infrastructure, you have access to compute and storage resources when you need them.

## Cost
  
You pay only for the compute power, storage, and other resources you use, with no long-term contracts or up-front commitments. For more information on comparing the costs of other hosting alternatives with AWS, see the AWS Economics Center.

#

## What is SRE?

 SRE (Site Reliability Engineer) - Role within tech industry that is responsible for understanding every core feature of a service/product and ensuring it's availability and usability throughout it's entire lifecycle.

 ### SRE traits
 - Studious
 - Problem Solver
 - Creative
 - Communicative
 - 

#

## AWS Global Infrastructure

The AWS Global Cloud is the most secure,extensive and reliable cloud platform that provides you the cloud infrastructure where and when you need it with a single-digit milisecond latency.

[![AWS Global Infrastructure map (click)](map.png)](https://aws.amazon.com/about-aws/global-infrastructure/regions_az/)
- 84 Availability zones with 26 total regions


#

## Regions VS Availability Zones

AWS Region concept:

- Physical location around the world where we cluster data centers. Each group of logical data centers are called Availability Zone.

Availability zone

- One or more discrete data centers with redundant power, networking, and connectivity in an AWS Region.

#

## Four pillars of cloud computing

### Performance

- Almost unlimited scalability
- Ability to quickly add nodes/servers/offerings (hybrid/public/private)

### Security

- Both physical and virtual security
- Protection against virtual threats i.e. DDoS, Leaks etc.
- Protection against physical threats i.e. destruction of servers, natural disasters, unauthorised access to the premises etc.

### Reliability

- Every possible scenario has been taken in consideration and prepared for.
- High availability(If you can't access it when you need it most it's not highly available)

### Functionality

- Modern use cases usually require the application of multiple analytic functions working together on the same data.
  
#
## What is CDN

Content Delivery Network refers to a geographically distributed group of servers that work together to provide fast delivery of Internet content.
#

## What is Auto-Scaling

Scaling (the server) with accordance to the demand.

#
## On Prem vs Hybrid vs Public Cloud

![diagrams](cloud_types.png)

### On Premises
- &nbsp;+ Highest level of security
- &nbsp;+ Best for storing sensitive data
- &nbsp;- &nbsp;Not cost Effective

### Hybrid
- &nbsp; +/- Medium cost efficiency
- &nbsp; + Best medium for storing sensitive data while providing cost effective service

### Public Cloud
- &nbsp; + Most cost effective
- &nbsp; - Sensitive data may be endangered
- &nbsp; + Worldwide coverage
  
#
### AWS VM connection diagram
![AWS connection diagram](paintDiagramLol.png)

Funny paint/gimp diagram but displays connection of a PC(localhost) to AWS via AWS IAM.

- file.pem - PEM stands for Privacy Enhanced Mail. The PEM format is often used to represent certificates, certificate requests, certificate chains, and keys. 
- .ssh folder - folder that contains .ssh files
    - SSH, also known as Secure Shell or Secure Socket Shell, is a network protocol that gives users, particularly system administrators, a secure way to access a computer over an unsecured network.
      - SSH uses port 22 [IMPORTANT]

- As long as the connection is exactly specified it is secure
- AWS IAM (Identity and Access Management) role is an IAM entity that defines a set of permissions for making AWS service requests. IAM roles are not associated with a specific user or group. Instead, trusted entities assume roles, such as IAM users, applications, or AWS services such as EC2.
- EC2 - Elastic Cloud Compute - provides scalable computing capacity in the AWS cloud. Leveraging it enables organizations to develop and deploy applications faster, without needing to invest in hardware upfront. Users can launch virtual servers, configure security and networking, and manage cookies from an intuitive dashboard.
  
#
### Creating of an EC2 Instance

- Login and access to AWS services
- Choose AMI (ubuntu 18.0.4)
- Choose EC2 Instance Types (default bc cheap lol)
- Configure Instance Details
  - Subnet choose "default a"
- Add storage
- Tag instance (for me it's 105_sre_adam_{purpose})
- Configure security groups
  - SSH on My Ip (port 22)
  - HTTP on anywhere (port 80)
  - HTTPS ONLY if you have ssl certificate
- Review instances
  - Select key name
- Launch :D
  
## ___________________

In a terminal window (preferably gitbash) follow steps from AWS:

The link should look like this: 

` ssh -i /path/my-key-pair.pem my-instance-user-name@my-instance-public-dns-name `

Once connected update all the required services via `sudo apt-get update -y` and `sudo apt-get upgrade -y` commands. Then install via `sudo apt-get install {name} -y`

Example: after installing nginx with a `sudo apt-get install nginx -y` command your output from the [website](http://34.244.154.49/) should look like this:

![picture](website_nginx.png)

#
### Linux basics

- add `sudo` before any command to use it with admin privelages
- start the service with `sudo systemctl start {service}`
- stop the service with `sudo systemctl stop {service}`
- to check the status use `systemctl status {service}`
- to enable the service use `sudo systemctl enable {service}`
- to install the service use `sudo apt-get install {package_name}`. To automate the command add `-y` parameter at the end of the command
- to uninstall the service use `sudo apt remove {package_name}`
- use `top` to show details of all active processes
- information of the system `uname` or `uname -a` (whoami)
- `pwd` print working directory (whereami)
- `mkdir {dir_name}` make directory(folder)
- `ls` to list all folders, with parameter `-a` lists all hidden folders
- how to create a file `touch name_file` or `nano file_name` (if you want to edit it straight after creating) or `cat > file_name` (if you want to edit it straight after within the commandline as a stream)
- to check contents of the file use `cat file_name`
- `mv file "new path for the file"` to move the file
  - make sure to provide quotations otherwise `mv file new_file_name` will change the name
- to delete a file (BE SURE ABOUT IT!) use `rm filename`

For the linux cheat sheet go [here](https://www.guru99.com/linux-commands-cheat-sheet.html)

### File permissions
- to check file permission type `ls -l`
- to edit file permission type `sudo chmod {rwx} filename` for example if you want readonly you use `sudo chmod r-- filename`
- rwx is described in binary form i.e. `sudo chmod 700` will create permission type of -rwx------
  - 0 = ---
  - 1 = --x
  - 2 = -w-
  - 3 = -wx
  - 4 = r--
  - 5 = r-x
  - 6 = rw-
  - 7 = rwx
- to check the file permissions `ll`
- [another cheat sheet](https://chmod-calculator.com/)

### Bash scripting

- code block
  ```bash
  # create a file called provision.sh
  #!/bin/bash
  # run updates
  sudo apt-get update -y
  # run upgrades
  sudo apt-get upgrade -y
  # install nginx
  sudo apt install nginx -y
  # ensure it's running - start nginx
  sudo systemctl start nginx
  # enable nginx
  sudo systemctl enable nginx

  ```

  - change the file to exe `chmod +x provision.sh`
  - how to run an exe file `./provision.sh`
  - 

## Tomcat
![kitty :3](Apache_Tomcat.png)
### Bash script for tomcat

```bash
#!/bin/bash
  # install tomcat
  sudo apt install tomcat9 -y
  # ensure it's running - start tomcat
  sudo systemctl start tomcat9
  # enable tomcat
  sudo systemctl enable tomcat9
  # allow traffic to port 8080
  sudo ufw allow from any to any port 8080 proto tcp
```
Apache Tomcat (called "Tomcat" for short) is a free and open-source implementation of the Jakarta Servlet, Jakarta Expression Language, and WebSocket technologies. Tomcat provides a "pure Java" HTTP web server environment in which Java code can run.

Remember that: 
- Tomcat runs on port 8080 so enable inbound for this port
- Tomcat may interfere with other web container services so be wary which services you want to run on which ports

Use cases for tomcat:
- Static page hosting
- Reverse proxy
- Dynamic web applications via Java Servlets and JSP
- Running WebSocket applications
- Load balancers

![tomcat def page](tomcat_itworks.png)

`default page of tomcat on port`

## NGINX 
![nginx](NGINX.png)

NGINX is open source software for web serving, reverse proxying, caching, load balancing, media streaming, and more. It started out as a web server designed for maximum performance and stability. In addition to its HTTP server capabilities, NGINX can also function as a proxy server for email (IMAP, POP3, and SMTP) and a reverse proxy and load balancer for HTTP, TCP, and UDP servers.

#
## Technical interview questions

What is a VPC

- A virtual private cloud (VPC) is a secure, isolated private cloud hosted within a public cloud. VPC customers can run code, store data, host websites, and do anything else they could do in an ordinary private cloud, but the private cloud is hosted remotely by a public cloud provider.

What is Internet gateway

- An Internet gateway is a network "node" that connects two different networks that use different protocols (rules) for communicating.
- In the most basic terms, an Internet gateway is where data stops on its way to or from other networks.
- Thanks to gateways, we can communicate and send data back and forth with each other.

What is route tables

- In computer networking, a routing table, or routing information base (RIB), is a data table stored in a router or a network host that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes.
- The routing table contains information about the topology of the network immediately around it.

What is a subnet

- A subnet, or subnetwork, is a network inside a network. Subnets make networks more efficient.
- Through subnetting, network traffic can travel a shorter distance without passing through unnecessary routers to reach its destination.

What is NACLS

- NACL refers to Network Access Control List, which helps provide a layer of security to the Amazon Web Services stack.
- NACL helps in providing a firewall thereby helping secure the VPCs and subnets.
- It helps provide a security layer which controls and efficiently manages the traffic that moves around in the subnets.
  
===================================================
- Security group is the firewall of EC2 Instances.
Network ACL is the firewall of the VPC Subnets.

===================================================

What is Security group

- A security group acts as a virtual firewall, controlling the traffic that is allowed to reach and leave the resources that it is associated with.
- For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

How did you secure your ap on the public cloud?

- Running tests on the app to determine limits of the public cloud
- Setting up Security Group / Server Firewall
- Installing/buying services that protect the instance against attacks designed to slow down/terminate the service

What are the outbound rules for SG by default? And why?

- Default SG starts with only one outbound rule that allows all traffic to leave the resource.
- You must add rules to enable any inbound traffic or to restrict the outbound traffic.
- A security group can be used only in the VPC for which it is created.

What is the command to kill a process in linux?

- `kill` command is used to send a signal to processes. The most frequently used one is `SIGKILL` or `-9` which terminates the given process
- Syntax `kill [OPTIONS] [PID]`
  - `[OPTIONS]` - type of signal
  - `[PID]` - Process ID number
  ![signals](signals.png)
- Most common way of using kill command is that instead of looking for specific PID we use `pidof {processname}` to find it i.e. to kill firefox process we'd use `kill -9 $(pidof firefox)`
- Sidenote: if you want to find PID yourself use `ps a` command. It'll display all running processes

#

## Monolith Architecture & Microservices Architecture

![monolith](microservices.png)
### Monolith Architecture


- One big service
- Simple but has limitations and complexity
- Heavy apps can slow down the startup tim
- Each update results into redeploying the full stack app
- Challenging to scale up
- Perfect for small services that don't require scaling

### Microservices Architecture

- Multiple small services
- User doesn't have direct access to any database
- Easily scalable (out and up)
- Adding features/services requires less refactoring
- Difficult to manage
- Expensive
- Most Secure
  
## 2- and N-tier Architecture

![blablapicture](2andNtierarch.png)

### 2- tier Architecture

- A two-tier architecture is a software architecture in which a presentation layer or interface runs on a client, and a data layer or data structure gets stored on a server.
- Separating these two components into different locations represents a two-tier architecture, as opposed to a single-tier architecture.

### N-tier Architecture

- An N-tier architecture divides an application into logical layers and physical tiers.
- Layers are a way to separate responsibilities and manage dependencies.
- Each layer has a specific responsibility.
- A higher layer can use services in a lower layer, but not the other way around.

#
### Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski
