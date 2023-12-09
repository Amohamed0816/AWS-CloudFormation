AWS CloudFormation Portfolio
Overview:
This CloudFormation template creates a robust AWS infrastructure portfolio, encompassing a Virtual Private Cloud (VPC) with public and private subnets, an internet gateway, a NAT gateway, security groups, an EC2 instance, an S3 bucket, an RDS instance, and associated resources.

Prerequisites

    AWS Account: You need an AWS account to deploy this CloudFormation template.
    AWS CLI: Install the AWS Command Line Interface to deploy the template from your local machine.

Parameters

    LabVpcCidr: CIDR block for the VPC.
    PublicSubnetCidr, PublicSubnetBCidr: CIDR blocks for public subnets.
    PrivateSubnetCidr, PrivateSubnetBCidr: CIDR blocks for private subnets.
    AmazonLinuxAMIID: AMI ID for Amazon Linux 2.

Resources Created

    VPC with Internet Gateway
        Creates a VPC with an internet gateway attached.

    NAT Gateway
        Creates a NAT gateway for private subnet internet access.

    Public and Private Subnets
        Creates public and private subnets in multiple availability zones.

    Route Tables
        Creates public and private route tables and associations.

    EC2 Instance
        Launches an EC2 instance with a user data script.

    S3 Bucket
        Creates an S3 bucket with private access.

    RDS Instance
        Creates an Aurora RDS instance.

    Security Groups
        Creates security groups for the EC2 instance and RDS instance.

    SNS Topic and Subscription
        Creates an SNS topic with an email subscription.

    CloudWatch Alarm
        Creates a CloudWatch alarm for EC2 CPU utilization.

Outputs

    LabVPCDefaultSecurityGroup: Default security group ID for the VPC.
    S3BucketName: Name of the S3 bucket.
    EC2InstanceId: ID of the EC2 instance.
    RDSInstanceEndpoint: Endpoint of the created RDS instance.

How to Deploy

    Clone the repository: git clone <repository-url>  
    Navigate to the project folder: cd <project-folder>
    Deploy the CloudFormation stack:
      - aws cloudformation create-stack --stack-name <stack-name> --template-body file://template.yaml --parameters ParameterKey=LabVpcCidr,ParameterValue=<vpc-cidr> ...
