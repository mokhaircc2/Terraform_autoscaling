**Terraform Autoscaling**

This project is about autoscaling an Apache Webserver using Terraform. This involved configuring a Launch Template, UserData scripts, ALB and CloudWatch Alarms to ensure scale out/in activities based on CPU metrics. In this project I created a VPC with public/private subnets, an ALB in the public subnet, Auto-Scaling Group in the private subnet and CloudWatch Alarms and policies based on desired metrics. At the end of the project please destroy the infrastructure using terraform destroy, so not to accumulate any costs.


Install Terraform from Hashicorp website

Create a Terraform user on AWS account. Go to IAM, user, and add user, give a name. Next select access key for programatic access. Next, attach existing policy directly and select AdministratorAccess and create user. You will be given an Access key ID and Secret Access key.

Use an IDE like Visual Studio Code

A provider in Terraform is a plugin that enables interaction using an API with the cloud providers. Create a file with the provider and initialise the backend.

The terraform init command initialises a working directory containing Terraform configuration files. This is the first command that should be run after writing a new Terraform configuration or cloning an existing one from version control.

Now create a VPC file which contains details of public/private subnets, Internet Gateway, route table for public/private subnets, Elastic IP and NAT Gateway

In the ALB file contains details about security group and ports used, Target Groups, Health Checks and listener.

In the Launch Template file there are details about security groups, AMI, instance type, user data.

Auto-Scaling Group file contains information about Max/Min number of instances, termination policies, scale in/out policies and alarms based upon desired metrics up/down.

Terraform plan, terraform apply and finally at the end of the project terraform destroy
