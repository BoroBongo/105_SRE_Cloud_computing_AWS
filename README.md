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
  # install nginx
  sudo apt install tomcat9 -y
  # ensure it's running - start nginx
  sudo systemctl start tomcat9
  # enable nginx
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
### Useful links

- https://www.comparethecloud.net/articles/the-four-pillars-of-an-enterprise-data-cloud/
- https://aws.amazon.com/application-hosting/benefits/
- https://www.instec-corp.com/instec-insights-the-four-pillars-of-cloud-computing
- https://www.guru99.com/creating-amazon-ec2-instance.html#3

#
#### ~Adam Franciszek Felix Kolaczynski
