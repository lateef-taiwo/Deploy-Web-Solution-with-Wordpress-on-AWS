# Deploy-Web-Solution-with-Wordpress-on-AWS
This repository explains the steps involved in  preparing storage infrastructure on two Linux servers and implementinga basic web solution using WordPress.

You will gain practical experience that demonstrates `three-tier architecture` while also making sure that the Linux servers' storage disks are properly partitioned and maintained using tools like `gdisk` and `LVM`, respectively. 

### The 3-Tier Setup
1. A Laptop or PC to serve as a client
2. An EC2 Linux Server as a web server (This is where you will install WordPress)
3. An EC2 Linux server as a database (DB) server

![Three tier](./images/Three%20tier%20architecture.png)


### PREPARE A WEB SERVER
* Launch an EC2 instance that will serve as "Web Server". I will choose Red hat Operating system for the servers.

* Login to the AWS console

* Search for EC2 (Elastic Compute Cloud)

* Select your preferred region (the closest to you) and launch a new EC2 instance and choose Red Hat

* Type a name e.g web-server Click create a new key pair, use any name of your choice as the name for the pem file and select `.pem`.

    * Linux/Mac users, choose .pem for use with openssh. This allows you to connect to your server using open ssh clients.
    
    * For windows users choose .ppk for use with putty. Putty is a software that lets you connect to servers remotely.

* Save your private key (.pem file) securely and do not share it with anyone! If you lose it, you will not be able to connect to your server ever again!

* On your local computer, open the terminal and change directory to the Downloads folder, type

    `cd ~/Downloads`

* Change permissions for the private key file (.pem), otherwise you can get an error “Bad permission”

    `sudo chmod 0400 . pem`

* Connect to the instance by running

   `ssh -i web-server.pem ec2-user@<public ip address>`

The public ip address of my virtual server is 13.40.64.167 as shown in the image Note: For Ubuntu server, the usernanme is ubuntu and for other servers like Fedora Amazon Machine image (AMI), the username is fedora or ec2-user.
