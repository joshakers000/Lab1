# Lab1
A cloudformation script containing (nearly) all requirements for creating a VPC with two subnets, 2 EC2 instances with one being private and one being public but able to ping each other. 


# What is created (custom)

- 1 VPC
- Two subnets in 2 different AZs (1 pub, 1 priv)
- 2 EC2 instances (1 pub, 1 priv)
- 1 IGW
- 2 RTs (1 pub, 1 priv)
- 2 NACLs (1 pub, 1 priv)
- - Several entries for both.
- Two security groups ( 1 for pub EC2, 1 for priv EC2)
- - Several entries for both.


# Security Concerns

- You opened ssh to all IPs!
- - NEVER DO THIS.  I am only doing this for the sake of ease while learning.  
- Your nacl/secGrp rules could use some work!
- - I am sure they could, I am will likely use this template in the future and improve upon this and more.  Just wanted to get this up and running.  
- You didn't attach the EC2 instances to the security groups!
- - This is the one manual thing you need to do if you launch this.  Otherwise you have to add them to the Network Interface entries.  For some reason you cannot add a security group AND a Network Interface to the same EC2 instance call in cloudformation.  
- No NAT GWs!
- - I had them in prior while testing.  I took them out as they're not free.  

# What is (nearly)?
- The EC2 instances are not added to their proper security groups as mentioned elsewhere.  You have to add them manually for now.  
- I do know now how to fix this.

# Other concerns
- There are no outputs on your script!
- - I am aware, I plan this to be part of a feature in a future lab.  
- Is it free?
- - Everything that's created should be free until your monthly usage exceeds the limit.  
- - No NAT GWs were created.
- I am seeing like 30 resources created!  What's the deal with that?
- Every entry in a NACL/secGrp counts as a resource, every association counts as a resource.  
- Why did you stop using your parameters?
- - This will be something I rectify later.  
