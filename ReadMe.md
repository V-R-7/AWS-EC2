# AWS-EC2
This is a documentation while I was learning to create an AWS EC2 Instance.

## Pre- Requisites :
AWS Account with IAM User with Admin permissions.

## Basics
Elastic Compute Cloud is known as EC2, It is an Infrastructure as service which allows users to run virtual servers, known as instances, in the cloud.

It offers capability of :
- Renting Virtual Machines (EC2)
- Storing data on virtual drives (EBS which is Elastic Block Storage, an AWS service)
- Distributes load across machines (ELB which is Elastic Load Balance, an AWS service)
- Scaling the services using an auto scaling group (ASG which is Auto Scaling group)

EC2 follows a pay-as-you-go pricing model, where you pay for the compute capacity you use.

Pricing is based on factors such as the instance type, region, and usage (On-Demand, Reserved Instances, or Spot Instances).

EC2 is versatile and can be used for a wide range of applications, including web hosting, application development and testing, big data analytics, and more.

## EC2 Configurations :

Choose an Amazon Machine Image (AMI) which is Operating System.
Choose how much compute power & cores (CPU)
Choose how much RAM (Random Access Memory) need to be configured.
Choose how much storage space - Network attached (EBS & EFS) or Hardware at EC2 Instance store.
Choose the Network card - speed and public IP address
Set Security Group i.e., Firewall Rules
Optional - EC2 User Data which is a bootstrap script (configure at first launch)


## Creating an EC2 Instance :

Login to AWS Management Console.

Navigate to EC2:
EC2 > Instances > Launch an instance

Before creating an Instance make sure the region you want is selected as desired.
- Select the region nearby.

Click on Launch Instance.

Now gonna create an AMI (An AMI is a template that contains the software configuration (operating system, application server, and applications) required to launch your instance.)
* Select an AMI - Amazon Linux 2023 AMI 2023
* Select an Instance Type - t2.micro
* Create a key pair with RSA keypair type & download .pem file to the computer (keep the file safe with you).
* Storage settings is set by default (can skip it)
* Final step click on Launch Instance

Now you can able to see your created instance in the portal.

## Connecting to EC2 Instance Using SSH :

- Install FileZilla if you do not have.
- To Connect the Instance using FileZilla
   - Go to File > Site Manager
   - Site Manager > Create New Site 
   - Select Protocol >  SFTP & Host - Set your Public IPV4 address and Port as 22
   - Logon Type > Normal
   - User > ec2-user ( For AMI - Amazon Linux 2023 AMI)
     Note : the user names will differ with AMI'S , refer below:

     The default user names are:

     1.For Amazon Linux 2023, Amazon Linux 2, or the Amazon Linux AMI, the user name is ec2-user.
     2.For a CentOS AMI, the user name is centos or ec2-user.
     3.For a Debian AMI, the user name is admin.
     4.For a Fedora AMI, the user name is fedora or ec2-user.
     5.For a RHEL AMI, the user name is ec2-user or root.
     6.For a SUSE AMI, the user name is ec2-user or root.
     7.For an Ubuntu AMI, the user name is ubuntu.
     8.For an Oracle AMI, the user name is ec2-user.
     9.For a Bitnami AMI, the user name is bitnami.
     Otherwise, check with the AMI provider.
     
   - Upload the .pem file which you downloaded when creating an instance to this instance.
   - Once done Go to your Instance and click on connect on the console.
     (EC2 > Instances > Your Instance)

## Connect to the Linux Instance
  Select Connection type > Connect using EC2 Instance Connect
  To connect to an instance using the instance ID and your own private key file:

  - If you want to connect to your instance over an EC2 Instance Connect Endpoint using your own private key, specify the instance ID and the path to the private key file. Do not include file:// in the path; the following example will fail: file:///path/to/key.(aws ec2-instance-connect ssh --instance-id i-1234567890example --private-key-file /path/to/key.pem)
  
  - Type the following command
    
    ```
    ssh \-i key-pair-name.pem ec2-user@Public IPv4 address
    ```
  - After typing the above command, you will face an issue like below image:

    ![279158615-5392ca8d-8110-42b5-8ea3-2162c1f571bc](https://github.com/V-R-7/AWS-EC2/assets/62888693/4b1a8cc8-8867-467e-893c-80b1e995cebb)

    Warning: UNPROTECTED PRIVATE KEY FILE! 
    It returns the above, so we must give permission using chmod.
    If you plan to use an SSH client on a macOS or Linux computer to connect to your Linux instance, use the following command to set the permissions of your private key file so that only you can read it

    ![image](https://github.com/V-R-7/AWS-EC2/assets/62888693/3248a293-b9c0-477f-a599-49da3b54c328)

  If you do not set these permissions, then you cannot connect to your instance using this key pair. For more information, see Error: Unprotected private key file.
  - Once typed chmod command , try the below command

      ```
      ssh -i key-pair-name.pem ec2-user@Public IPv4 address
      ```
  - Finally you will be able to login your created Instance.

    ![279161655-48870187-a05c-4f0b-b199-86114145c51e](https://github.com/V-R-7/AWS-EC2/assets/62888693/d27a9f7b-ff98-4b9e-9b0b-081eba32e965)

   Congratulations! You have successfully configured an EC2 instance 🎉.

I have added folders for specific topics on EC2 for more learning.
