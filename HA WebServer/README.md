
# High Availability AWS Web Application with WAF

## Overview

This project demonstrates the deployment of a high-availability web application on Amazon Web Services (AWS) using CloudFormation templates. The architecture includes an Application Load Balancer (ALB), Amazon RDS for a database, AWS WAF for a web application firewall, and EC2 instances distributed across multiple availability zones.

## Design

![image](https://github.com/Amohamed0816/AWS-CloudFormation/assets/127431316/c4ca2ad2-76ff-4ef4-8204-22c9f377c52c)


## Architecture

The architecture of the project is designed to ensure high availability, fault tolerance, and security. Key components include:

- **Virtual Private Cloud (VPC):** A VPC is set up with multiple availability zones to enhance availability and fault tolerance.

- **Public Subnet:** Contains an ALB for distributing traffic, and a NAT Gateway for internet access.

- **Private Subnets (A and B):** Each contains EC2 instances (web servers) and an RDS database, ensuring a secure and isolated environment.

- **ALB:** The Application Load Balancer distributes incoming web traffic across EC2 instances in private subnets, improving application availability.

- **Auto Scaling:** EC2 instances are configured with Auto Scaling to automatically adjust to changing traffic patterns.

- **Amazon RDS:** A multi-AZ RDS database setup ensures data durability and availability.

- **WAF Integration:** AWS WAF is employed to protect against web application attacks and provides an additional layer of security.

- **S3 Bucket:** Used for storing and managing static assets (Make sure to name your own S3 Bucket in the template).

## Deployment

The infrastructure is deployed using AWS CloudFormation templates. The templates define the network architecture, security groups, EC2 instances, RDS instances, ALB, and other components.

## Usage

1. Clone the repository.
2. Use CloudFormation to deploy the templates.
3. Access the web application via the ALB's public DNS or IP.

## Customization

The templates can be easily customized to adapt to specific requirements, such as changing instance types, modifying security groups, or adding additional components.

## Security

- Security groups are implemented for controlling inbound and outbound traffic to instances.
- AWS WAF provides protection against common web application attacks.
- Private subnets enhance the security posture of EC2 instances and databases.

## Future Enhancements

Future enhancements could include the integration of additional AWS services, continuous integration and deployment (CI/CD) pipelines, and monitoring solutions for better insights into the application's performance.

---

Feel free to tailor this overview to your specific project details and preferences.
