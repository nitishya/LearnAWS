AWS(Amazon Web Seevices) - Cloud Provider 
->Provide you with servers and services that you can use on demand and scale easily.

2002  -> 2003 -> 2004 -> 2006 --> 2007 -->

AWS Regions ---
AWS has regions all around the world like us-east-I,eu-west-3
A region is a cluster of data centers.
Most AWS services are region scoped

Question - How to choose a AWS region?
1-Compliance with data goverannce anf legal requirements:data never leaves a region without your explicit permission.
2-Proximity to customers:reduced latency
3-Available Services within a Region -new features and services are not available in all region.
4-Pricing it varies from region to region .


AWS Availability Zones 
1-Each region has many availability zones (usually 3,min is 3,max is 6)
2-Each AZ is one or more dicrete data centers with redundant power,networking and connectivity.
3-They are separated from each other,so that they are isolated from disasters

[logo]:https://www.w3schools.com/aws/images/availabilityzones.png "Logo Title Text 2"


AWS Points of Presence(Edge Locations)-
->Helpful in delivery content to end users with lower latency


AWS Global Services -
1)IAM
2)Route 53
3)CloudFront
4)WAF

AWS Services region Scoped-
1)EC2
2)Elastic BeanStalk
3)Lambda
4)Rekognition


**IAM Section ->** 

- IAM = Identity and Access Management, Global Service
- Root account created by default, shouldn't be used or shared
- User are the people within your organisation and can be grouped.
- Groups only contain users, not other groups
- User dont have to belong to a group and user can belong to multiple groups

IAM permissions - users and  groups can be assigned JSON documents called policies.
                - These policies define the permisssions of the users.
                - Least Privilage Principle , dont give more permissions than a user needs.

IAM Policies Inheritance -Structure
Version,ID,statement
Statement-sid,Effect,Principal,Action,Resource,Condition

IAM Password Policy 
- Strong passwords = high security for your account
- In AWS you can setup a password policy:
- Set a minimum password length
- Require specific character types:including uppercase letters ,lowercase letters, numbers, non-alphanumeric characters
- Allow all IAM users to change their own passwords
- Require users to change their password after sometime
- Prevent password reuse

Multi Factor Authentication -MFA 
MFA = password you know + security device you own
MFA in AWS - Virtual MFA device , AUthy ,Universal 2nd Factor(U2F) Security key(Yubikey)


What is AWS CLI ?
A tool that enables you to interact with AWS services using commands in your command line shell.

What is AWS SDK?
- AWS software Development Kit(AWS SDK)
- Language Specific APIs(Set of libraries)
- Enables you to access and manage AWS programmaticaly
- Embedded within your application
- Supports c++,java,nodejs,ruby,python

**AWS CLI HANDS ON**
  aws --version
  aws configure 
  key ID
  Secret id
  region 
  output 
  aws iam list-users

**AWS Cloudshell**
aws --verion
terminal in aws cloud which is free to use
ls
echo "text" > demo.txt
cat demo.txt
pwd

**IAM Roles for Services**
Assign permission to AWS services with IAM ROle
Common Roles 
- EC2 Instance roles
- Lambda Function roles
- Roles for cloud Formation

**IAM Security Tools**
- IAM Credential Report(account-level) : a report that lists all your accounts users and the status of their various credentials
- IAM Access Advisor(user level) : Access advisor shows the service permissions granted to a user and when those services were last accessed.

**IAM Guidelines and Best Practices**
- Dont use the root account except for AWS account setup
- One physical user = one AWS user
- Assign users to groups and assign permissions to groups
- Create a strong password policy
- Use and enforce the use of Multi Factor Authentication(MFA)
- Use access Keys for programmatic Access(CLI/SDK)
- Audit permissions of your account using IAM Credentials Report & IAM Access Advisor
- Never share IAM users & Access Keys


**Shared Responsibily Model**

| Features       | AWS          | YOU  |
| ------------- |:-------------:| -----:|
| 1             | Infrastructure(Global national Security)  | User,Groups,Roles,Policies management and monitoring |
| 2             | Configuration and vulnerability analysis  | Enable MFA on all accounts|
| 3             | Compliance Validation                     |    Rotate your keys often |
| 4             | .....                                     | Use IAM tools to apply appropriate permissions 
| 5             |   .....                                   | Analyse access patterns and review permissions


---

**Amazon EC2**
- most popular of AWS offering
- EC2= Elastic Compute Cloud = Infrastructure as a Service.
- It mainly consists in the cpability of :
    - Renting virtual machines(EC2).
    - Storing data on virtual drives(EBS).
    - Distributing load across machines(ELB).
    - Scaling the services using an auto-scaling group(ASG).

- EC2 sizing and configuration options
   - Operating OS
   - how much compute power and cores
   - how much ram
   - how much storage space- network attatched(EBS & EFS) , hardware(EC2 instance store)
   - Network card: speed of the card, Public IP address
   - Firewall reules:security group
   - Bootstrap script(configure at first launch): EC2 user data
   - Bootstrapping means launching commands when machine starts.
   - That script is only run once at the instance first start
   - EC2 user data is used to automate boot tasks such as installing updates,installing software,downloading common files from the internet.
   - EC2 User data script runs with the root user.
   - instance types: t2.micro , t2.xlarge ,c5d.4xlarge,r5.16xlarge,m5.8xlarge
   - ![image](https://github.com/user-attachments/assets/735bea61-5a31-4e44-bce7-bc4f7bff4fc8)
 
EC2 instance-General Purpose
- Great for diversity of workloads such as web servers or code repositories
- Balance between
  - compute
  - memory
  - networking

You can view information about the instances on  https://instances.vantage.sh/

Security Groups 
- Security groups are the fundamental of network security in AWS
- They control how traffic is allowed into or out of our EC2 instances
- Security groups only contain allow rules
- Security groups rules can reference by IP or by security group
- Security groups are acting firewall on the EC2 instances
- They regulate
    - Access to ports
    - Authorised IP ranges - IPv4 and IPv6
    - Control of inbound network(from other to the instance )
    - Control of the outbound network (from the instance to other)

- Classic Ports to know
    - 22 = SSH(Secure Shell) - log into a Linux instance
    - 21 = FTP(File Transfer Protocol) - upload files into a file share
    - 22 = SFTP(Secure File Transfer Protocol) - upload files using SSH
    - 80 = HTTP - access unsecured websites
    - 443 = HTTPS - access secured websites
    - 3389 = RDP(Remote Desktop Protocol) - log into a Windows instance
 
  **SSH**
  - SSh(Secure shell) is the one of the most important function.It allows you to control a remote machine, all using command line.
 
  - 

   


  
  


