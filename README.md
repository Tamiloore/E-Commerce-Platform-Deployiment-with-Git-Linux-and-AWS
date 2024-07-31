# Capstone Project: E-Commerce-Platform-Deployment-with-Git-Linux-and-AWS
## Project Description:
To develop an e-commerce website for a new online marketplace name "Agate Interior". This platform will feature product listings, a shopping cart, and user authentication.
## Task:
1. To utilize Git for version control, develop the platform in a linux environment, and deploy it on an AWS EC2 instance.
2. Continous integration and development workflow 
-  Developing New features and fixes 
- Version Control with Git 
- Pull Requests and Merging to ain branch 
- Deploying Updates to the production Server 
- Testing the new changes 

## Step 1: 
### Initialize Git Repository
- Create a new Repository 

 ![alt text](Img/1_aws.png)

 - Copy SSH/HTTP (depending on the one you use best)
 
 ![alt text](Img/2_aws.png)

 - Clone the Repo
 `git clone "Paste the URL"`

 - Confirm it has been successfully downloaded into your local Repo

 ![alt text](Img/3_aws.png)

 ## Step 2: 
### Obtain and Prepare the E-Commerce Website Template
Instead of developing the website from scratch, use a pre-existing e-commerce website template

- Download A website template from (https://www.tooplate.com/) or any website template hub you know 

![alt text](Img/4_aws.png)

- Extract the Downloaded template into your project Directory that you've created 

- Customize the template if you have a basic web development skill. (I Tailored mine to Agate Interior)

![alt text](Img/5_aws.png)

 ## Step 3: 
### Stage and Commit the Template to Git

- Run `ls` to cnfirm the directory
- `git add "Directory_name"` to stage the codes

![alt text](Img/6_aws.png)

- Run `git status` to see if it's succefully staged 

![alt text](Img/7_aws.png)

- Run `git commit -m "your message"` to commit your code 

![alt text](Img/8_aws.png)

- `git push` / `git push -u origin main` to push your code to your remote Repo

![alt text](Img/9_aws.png)

- Go to your Github to confirm the changes

![alt text](Img/10_aws.png)

 ## Step 4: 
### AWS Deployment
To deploy, you'll start by setting up an Amazon EC2 instance 

- Log in to the AWS Management Console 

![alt text](Img/11_aws.png)

- Launch An EC2 Instance Using an Amaxon Linux AMI

- Remember to download a keypair 

![alt text](Img/12_aws.png)

![alt text](Img/13_aws.png)

- Connect to the to your local Repo using SSH
- Copy the URL

![alt text](Img/14_aws.png)

You have succesfully launch an EC2

 ## Step 5: 
### Connect and Clone the repository on the Linux Server
You need to clone the GitHub repositotry to your AWS EC2 instance. This process involves authenticating with Github using SSH

- Open your Local Server 
- Paste the URL copied from your EC2 to connect your local server to the remote server 

![alt text](Img/15_aws.png)

- Run `ssh-keygen` to generate an SSH keypair

- Press enter to use the default file directory and passphrase

![alt text](17_aws.png)

- Run `cat /home/ec2-user/.ssh/id_rsa.pub` (copy the content)

![alt text](18_aws.png)

- Navigate to your Repository in GitHub Console, click on settings

![alt text](19_aws.png)

- Navigate to SSH and GPG key, create new SSH key 

![alt text](21_aws.png)

- Paste the Copied content, and add SSH key

![alt text](22_aws.png)

### Install git on your EC2 server if you have it installed 

To check if it is installed ot not 

- Run `which git`

![alt text](23_aws.png)

- To install, run `sudo yum install git`

![alt text](24_aws.png)

### Clone the Repository

- Navigate back to Repo and copy the SSH URL

![alt text](Img/16_aws.png)

- Clone Repo

![alt text](25_aws.png)

 ## Step 6: 
### Install a Web Server on EC2

### Apache HTTP Scerver 
Installing it on Linux EC2 server allows you to host "**Agate Interior**" 

- Install Apache web server on the EC2 instance.


```sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

![alt text](26_aws.png)

- Configure httpd for website 

```
sudo rm -rf /var/www/html/*
sudo cp -r ~Agate_interior/* /var/www/html/
```
![alt text](27_aws.png)


- Reload httpd 

`sudo systemctl reload httpd`

![alt text](28_aws.png)

 ## Step 7: 
### Sccess Website from browser 

- Open a web browser and acess the pubic IP of your EC2 instance to view the deployed website 

![alt text](29_aws.png)

 ## Step 8: 
### Continuous Integration and Deployment Workflow

- Developing New Features and fixes 

- `git checkout -b Development` to create new branch

![alt text](30_aws.png)

- Make your New development 

![alt text](31_aws.png)

- Stage your Edit

```
git add "index.html"
git commit -m "your message"
git push
```

![alt text](32_aws.png)

- Go to your GitHub 

![alt text](33_aws.png)

![alt text](34_aws.png)

![alt text](35_aws.png)

- Git pull 

![alt text](36_aws.png)

## Step 8: 
### Deploying Updates to the Production Server 

- Pull the latest changes on the Server 

![alt text](Img/37_aws.png)

- Follow and study the code 

![alt text](Img/38_aws.png)


- Code Updated

## Before 
![alt text](Img/5_aws.png)

## After
![alt text](Img/39_aws.png)



