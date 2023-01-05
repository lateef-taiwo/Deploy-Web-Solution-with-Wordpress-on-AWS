# Deploy-Web-Solution-with-Wordpress-on-AWS
This repository explains the steps involved in  preparing storage infrastructure on two Linux servers and implementinga basic web solution using WordPress.

You will gain practical experience that demonstrates `three-tier architecture` while also making sure that the Linux servers' storage disks are properly partitioned and maintained using tools like `gdisk` and `LVM`, respectively. 

### The 3-Tier Setup
1. A Laptop or PC to serve as a client
2. An EC2 Linux Server as a web server (This is where you will install WordPress)
3. An EC2 Linux server as a database (DB) server

![Three tier](./images/Three%20tier%20architecture.png)


### PREPARE A WEB SERVER
* Launch an EC2 instance that will serve as "Web Server". I will choose Red hat Operating system for the servers. Create 3 volumes in the same AZ as your Web Server EC2, each of 10 GiB. 

* Login to the AWS console

* Search for EC2 (Elastic Compute Cloud)

* Select your preferred region (the closest to you) and launch a new EC2 instance of t2.micro family with Ubuntu Server 20.04 LTS (HVM)
    Type a name e.g web-server Click create a new key pair, use any name of your choice as the name for the pem file and select `.pem`.

    * Linux/Mac users, choose .pem for use with openssh. This allows you to connect to your server using open ssh clients.
    
    * For windows users choose .ppk for use with putty. Putty is a software that lets you connect to servers remotely.

* Save your private key (.pem file) securely and do not share it with anyone! If you lose it, you will not be able to connect to your server ever again!
