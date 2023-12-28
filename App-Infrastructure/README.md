# Capstone Project: AWS Cloud Infrastructure Deployment

## Overview

This Capstone Project showcases the deployment of a basic AWS infrastructure using CloudFormation, designed as part of a job application portfolio. The project aims to demonstrate proficiency in Infrastructure as Code (IaC), AWS service integration, and best practices for creating a scalable and secure environment.

## Design

![CloudFormation Template drawio](https://github.com/Amohamed0816/AWS-CloudFormation/assets/127431316/aaadcc44-bdca-43a3-b4c6-e68ffbda86e9)

## Architecture

- **Virtual Private Cloud (VPC):** Establishes a VPC with public and private subnets, internet gateway, and NAT gateway to create a secure and scalable network architecture.

- **Amazon RDS (Relational Database Service):** Sets up an RDS instance with the MySQL engine (version 5.7), demonstrating the configuration of a reliable and managed database solution.

- **Amazon S3 Bucket:** Creates a private S3 bucket with specified access controls, showcasing object storage and data management capabilities (Make sure to name your own S3 Bucket in the template).

- **EC2 Instance:** Launches an EC2 instance with Amazon Linux 2 AMI, demonstrating the deployment of a web server using user data scripts.

- **Monitoring and Notifications:** Utilizes CloudWatch Alarms to monitor the EC2 instance's CPU utilization, with notifications sent via Amazon SNS (Simple Notification Service) for threshold breaches (Make sure to add your email address in the template SNS notification to receive the notifications).

## How to Use

1. **Deployment:**
   - Deploy the CloudFormation template using the AWS Management Console, AWS CLI, or other tools.
   - Customize parameters such as VPC CIDR, subnet CIDRs, and other inputs during deployment.

2. **Accessing Resources:**
   - Access deployed resources like the EC2 instance, RDS instance, and S3 bucket based on specific application requirements.

3. **Monitoring:**
   - Monitor the EC2 instance's CPU utilization through the configured CloudWatch alarm.

## Important Notes

- Ensure proper AWS credentials and permissions for successful template deployment.
- Customize parameters to align with specific use cases.
- Refer to the CloudFormation documentation for detailed information on template parameters and resource configurations.

## Contributing

Contributions and improvements to this project are welcome. Feel free to open issues or pull requests.

## License

This project is licensed under the [MIT License](LICENSE).



