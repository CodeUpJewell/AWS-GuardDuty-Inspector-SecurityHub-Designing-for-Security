# Designing-for-Security

This is the third major project in Udacity AWS Cloud Architect Nanodegree.

In this project, you will plan, design, provision, and monitor infrastructure in AWS using industry-standard and open source tools. You will practice the skills you have learned throughout the course to optimize infrastructure for cost and performance. You will also use Terraform to provision and configure AWS services in a global configuration.

Project Files

 As a Cloud Architect, you have been asked to apply security best practices to the environment so that it can withstand attacks and be more secure.
 
    E1T4.txt: Identify 2-3 changes that can be made to our environment to prevent an SSH brute force attack from the internet. Neither instance should have had access to the secret recipes bucket; even in the instance that API credentials were compromised how could we have prevented access to sensitive data?

    E2T2.txt: Research and analyze which of the vulnerabilities appear to be related to the code that was deployed for the environment in this project. We then provide recommendations on how to remediate the vulnerabilities.
    
    E3T1.txt: What findings were detected related to the brute force attack? AWS GuardDuty documentation and explanation of what was it's source of information?
    
    E4T1.txt: Text file listing 2-3 changes that can be made to environment to prevent an ssh brute force attack from the internet and also 2-3 points about how to secure the sensitive data in S3.
   
    E4T4.txt: What additional architectural change can be made to reduce the internet-facing attack surface of the web application instance. 
    Assuming the IAM permissions for the S3 bucket are still insecure, would creating VPC private endpoints for S3 prevent the unauthorized access to the secrets bucket? 
    
    Will applying default encryption setting to the s3 buckets encrypt the data that already exists? The changes you made above were done through the console or CLI; describe the outcome if the original cloud formation templates are applied to this environment?


    E5T2.txt: You will need to determine appropriate tools to incorporate into the pipeline to ensure that security vulnerabilities are found. 
    
    Identify tools that will allow you to do the following: a. Scan infrastructure as code templates. b. Scan AMI’s or containers for OS vulnerabilities. c. Scan an AWS environment for cloud configuration vulnerabilities. For each tool we identify an example compliance violation or vulnerability which it might expose.

    
    Free_recipe.txt: Text file containing our mother's delicious Banana Bread recipe.
    secret_recipe.txt: Text file containg our secret delicious recipe. Should only be given to those with the appropriate permissions.
    
In this task, the objective is to familiarize yourself with the starter code and to get you up and running quickly. Spend a few minutes going through the .yml files in the starter folder to get a feel for how parts of the code will map to the components in the architecture diagram.

Additionally, we utiilize CloudFormation templates which will deploy the following resources in AWS:
VPC Stack for the underlying network:

    c3-vpc.yml:
    A VPC with 2 public subnets, one private subnet, and internet gateways etc for internet access.

S3 bucket stack:

    c3-s3_solution.yml:
    2 S3 buckets that will contain data objects for the application.

Application stack:

    c3-app_solution.yml:
    An EC2 instance that will act as an external attacker from which we will test the ability of our environment to handle threats
    An EC2 instance that will be running a simple web service.
    Application LoadBalancer
    Security groups
    IAM role

    c3-s3_solution.yml: CloudFormation template that deploys an S3 bucket for storage of recipes woth default encryption enabled.
    c3-app_solution.yml: CloudFormation template that deploys ec2 instances for the project starter. Security group rules only accept traffic from specific ports in this template.
