# Capstone Project: E-Commerce-Platform-Deployment-with-Git-Linux-and-AWS
## Project Description:
To develop an e-commerce website for a new online marketplace name "Agate Interior". This platform will feature product listings, a shopping cart, and user authentication.
## Task:
1. To utilize Git for version control, develop the platform in a Linux environment, and deploy it on an AWS EC2 instance.
2. Continous integration and development workflow 
-  Developing New features and fixes 
- Version Control with Git 
- Pull Requests and Merging to ain branch 
- Deploying Updates to the Production Server 
- Testing the new changes 

## Step 1: 
### Initialize Git Repository
- Create a new Repository 

 ![1_aws](https://github.com/user-attachments/assets/a9009396-a6df-4d73-b68b-8929c275062d)


 - Copy SSH/HTTP (depending on the one you use best)
   
 ![2_aws](https://github.com/user-attachments/assets/ca5140fc-909b-40eb-a912-dd827a7de633)

 - Clone the Repo
 `git clone "Paste the URL"`

 - Confirm it has been successfully downloaded into your local Repo

![3_aws](https://github.com/user-attachments/assets/89f8d1c8-5712-4906-a354-cdb518ca499b)

 ## Step 2: 
### Obtain and Prepare the E-Commerce Website Template
Instead of developing the website from scratch, use a pre-existing e-commerce website template

- Download A website template from (https://www.tooplate.com/) or any website template hub you know 

![4_aws](https://github.com/user-attachments/assets/f6665189-bfa8-4e02-a444-27c53e8c1849)

- Extract the Downloaded template into your project Directory that you've created 

- Customize the template if you have a basic web development skill. (I Tailored mine to Agate Interior)

![5_aws](https://github.com/user-attachments/assets/cad4b981-5a0b-4d47-918d-1559196b2cab)

 ## Step 3: 
### Stage and Commit the Template to Git

- Run `ls` to confirm the directory
- `git add "Directory_name"` to stage the codes

![6_aws](https://github.com/user-attachments/assets/40323672-d1d7-4228-9613-510a75ffb731)


- Run `git status` to see if it's successfully staged 

![7_aws](https://github.com/user-attachments/assets/3bb453d8-4164-4307-9284-10fa4c12876b)

- Run `git commit -m "your message"` to commit your code 

![8_aws](https://github.com/user-attachments/assets/7011f346-dc54-4f07-8567-372a7a6a5579)

- `git push` / `git push -u origin main` to push your code to your remote Repo

![9_aws](https://github.com/user-attachments/assets/0ef69855-94c7-4a2c-97d1-abbc17c0fe55)

- Go to your Github to confirm the changes

![10_aws](https://github.com/user-attachments/assets/2598647e-6f29-409e-8c1b-4adf636635b4)

 ## Step 4: 
### AWS Deployment
To deploy, you'll start by setting up an Amazon EC2 instance 

- Log in to the AWS Management Console 

![11_aws](https://github.com/user-attachments/assets/b9b4ca0f-f7b2-4188-b950-10d0cac4d6ef)

- Launch An EC2 Instance Using an Amazon Linux AMI

- Remember to download a key pair 

![12_aws](https://github.com/user-attachments/assets/b18fd308-996d-412d-ab16-4c918936bd34)

![13_aws](https://github.com/user-attachments/assets/c28f0ada-8907-4b10-9c1e-2bf3f97caf25)


- Connect to the to your local Repo using SSH
- Copy the URL

![14_aws](https://github.com/user-attachments/assets/ee199d64-3d35-4038-a456-98641f94de77)

You have successfully launched an EC2

 ## Step 5: 
### Connect and Clone the repository on the Linux Server
You need to clone the GitHub repository to your AWS EC2 instance. This process involves authenticating with GitHub using SSH

- Open your Local Server 
- Paste the URL copied from your EC2 to connect your local server to the remote server 

![15_aws](https://github.com/user-attachments/assets/5f504e78-51a4-4ded-979d-67ea3138eedf)

- Run `ssh-keygen` to generate an SSH keypair

- Press enter to use the default file directory and passphrase

![17_aws](https://github.com/user-attachments/assets/d758ead1-48ab-4a9c-aa28-4c447ae40bd6)


- Run `cat /home/ec2-user/.ssh/id_rsa.pub` (copy the content)

![18_aws](https://github.com/user-attachments/assets/8652e3a1-53b3-4dcb-98d7-a8d2e1408560)

- Navigate to your Repository in GitHub Console, click on settings

![19_aws](https://github.com/user-attachments/assets/9855ee82-5c7d-4483-b7e9-dac0d11fd17c)


- Navigate to SSH and GPG key, create a new SSH key 

![21_aws](https://github.com/user-attachments/assets/45f43795-30ff-4c6c-a44f-919f2f30f250)


- Paste the Copied content, and add the SSH key

![22_aws](https://github.com/user-attachments/assets/c913ed71-480f-47f5-bae6-8ce2ace68e2d)

### Install git on your EC2 server if you have it installed 

To check if it is installed or not 

- Run `which git`

![23_aws](https://github.com/user-attachments/assets/8533f953-c0df-4fc8-b113-ec59589726ea)


- To install, run `sudo yum install git`

![24_aws](https://github.com/user-attachments/assets/44662ae0-ff21-44df-8f06-6216101aaae9)

### Clone the Repository

- Navigate back to Repo and copy the SSH URL

![16_aws](https://github.com/user-attachments/assets/54c81ffe-c749-4c03-b558-aae7bb4ed2f5)

- Clone Repo

![25_aws](https://github.com/user-attachments/assets/54071175-143c-4854-9f81-c5be470d36d5)


 ## Step 6: 
### Install a Web Server on EC2

### Apache HTTP Scerver 
Installing it on Linux EC2 server allows you to host "**Agate Interior**" 

- Install the Apache web server on the EC2 instance.


```sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```

![26_aws](https://github.com/user-attachments/assets/712c8886-82dc-42ca-8d4b-40577afaea5b)


- Configure httpd for the website 

```
sudo rm -rf /var/www/html/*
sudo cp -r ~Agate_interior/* /var/www/html/
```
![27_aws](https://github.com/user-attachments/assets/c30988d7-37e1-4432-9094-19e8494edfc5)

- Reload httpd 

`sudo systemctl reload httpd`

![28_aws](https://github.com/user-attachments/assets/d812c2bd-9b98-40f8-bab5-df2656cef989)

 ## Step 7: 
### Sccess Website from browser 

- Open a web browser and access the public IP of your EC2 instance to view the deployed website 

![29_aws](https://github.com/user-attachments/assets/773eb3fd-c411-4a57-8aba-3a23fe91f0d4)


 ## Step 8: 
### Continuous Integration and Deployment Workflow

- Developing New Features and fixes 

- `git checkout -b Development` to create a new branch

![30_aws](https://github.com/user-attachments/assets/e53e20fd-47d8-469f-b560-8f3d0eefcaf2)


- Make your New development 

![31_aws](https://github.com/user-attachments/assets/734c509c-a8d1-4a0b-9f92-e3a8b40f4f12)

- Stage your Edit

```
git add "index.html"
git commit -m "your message"
git push
```

![32_aws](https://github.com/user-attachments/assets/4ec1d03a-0d71-48e3-aa1f-32fd8973d5a0)


- Go to your GitHub 

![33_aws](https://github.com/user-attachments/assets/a8819b6c-0f63-448d-aac7-19730160069b)


![34_aws](https://github.com/user-attachments/assets/f101f095-c585-4b3d-8b5f-d49c204a1575)


![35_aws](https://github.com/user-attachments/assets/47da77a5-d546-4b29-be43-b46d40dde310)


- Git pull 

![36_aws](https://github.com/user-attachments/assets/86948c08-c36c-407c-9924-6e949faf3a47)


## Step 8: 
### Deploying Updates to the Production Server 

- Pull the latest changes on the Server 

![37_aws](https://github.com/user-attachments/assets/366e2aef-a832-428f-87a0-a4c133a35de3)


- Follow and study the code 

![38_aws](https://github.com/user-attachments/assets/2d9ef45a-c875-40c7-b62f-90bf829eb4a8)



- Code Updated

## Before 
![5_aws](https://github.com/user-attachments/assets/cad4b981-5a0b-4d47-918d-1559196b2cab)

## After
![39_aws](https://github.com/user-attachments/assets/8ac29c0a-e023-4932-9e86-9b0c6bb434e2)




