CloudFormation
=========

Launce_EC2.yml cloudformation script launch ec2 instance with

 1) RHEL 7 Amazon Machine Image.  
 2) Attach 30 GB volume to EC2 instance.  
 3) Attach IAM role to EC2 machine with list and get s3 permissions.  
 4) Configure aws_cfn , mount attached volume and enable RedHat subscription.   

Parameters
------------

**InstanceType**  
Select AWS EC2 instance type e.g t2.medium.  

**KeyName**  
SSH key to connect EC2 instance.


