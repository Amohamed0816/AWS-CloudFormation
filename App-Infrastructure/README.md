AWS CloudFormation Portfolio

Capstone Application CloudFormation Template

Overview

This CloudFormation template is designed as part of a capstone project for a job application, showcasing the creation of a basic AWS infrastructure. The template leverages AWS services to set up a Virtual Private Cloud (VPC) with public and private subnets, an internet gateway, a Network Address Translation (NAT) gateway, Amazon RDS (Relational Database Service), an EC2 instance, an S3 bucket, and additional components.

Diagram:

![CloudFormation Template drawio](https://github.com/Amohamed0816/AWS-CloudFormation/assets/127431316/aaadcc44-bdca-43a3-b4c6-e68ffbda86e9)

Key Components

    VPC Setup:
        Creates a VPC with a specified CIDR block, enabling DNS support and hostnames.
        Establishes an internet gateway and attaches it to the VPC for public internet access.
        Configures two public subnets and two private subnets across multiple Availability Zones (AZs).

    NAT Gateway:
        Allocates an Elastic IP (EIP) for the NAT gateway.
        Deploys a NAT gateway in the public subnet to enable private instances to access the internet.

    Route Tables:
        Creates public and private route tables for associating with the corresponding subnets.
        Configures routes, directing public traffic to the internet via the internet gateway and private traffic through the NAT gateway.

    Security Groups:
        Defines security groups for applications (AppSecurityGroup) and relational databases (MyDBSecurityGroup).
        Configures ingress rules to control traffic access for the specified ports.

    Amazon RDS (Relational Database Service):
        Launches an RDS instance with MySQL engine, version 5.7, in the specified subnets.
        Configures a DB subnet group for the RDS instance.

    S3 Bucket:
        Creates a private S3 bucket with the specified name and access control settings.

    EC2 Instance:
        Launches an EC2 instance with Amazon Linux 2 AMI in the public subnet.
        Configures the instance with a simple user data script, installing and starting an Apache web server.

    SNS Topic and Subscription:
        Establishes an SNS topic named 'MySNSTopic.'
        Subscribes an email address ('amohamed.0816@gmail.com') to receive notifications from the SNS topic.

    CloudWatch Alarm:
        Sets up a CloudWatch alarm monitoring the CPU utilization of the EC2 instance.
        Configures the alarm to send notifications to the specified SNS topic when the threshold is breached.

Instructions for Use

    Deploying the Template:
        Use the AWS Management Console, AWS CLI, or other tools to deploy the CloudFormation template.
        Define necessary parameters like VPC CIDR, subnet CIDRs, and other inputs during deployment.

    Accessing Resources:
        Access the deployed resources such as the EC2 instance, RDS instance, and S3 bucket based on your application requirements.

    Monitoring and Notifications:
        Monitor the EC2 instance's CPU utilization through the CloudWatch alarm.
        Receive email notifications for CPU threshold breaches through the configured SNS topic.

Important Notes

    Ensure that AWS credentials and necessary permissions are set up for successful template deployment.
    Customize parameters as needed for your specific use case.
    Refer to the CloudFormation documentation for more details on template parameters and resource configurations.

How to Deploy

    Clone the repository: git clone <repository-url>  
    
    Navigate to the project folder: cd <project-folder>
    
    Deploy the CloudFormation stack:
    
      - aws cloudformation create-stack --stack-name <stack-name> --template-body file://template.yaml --parameters ParameterKey=LabVpcCidr,ParameterValue=<vpc-cidr> ...
