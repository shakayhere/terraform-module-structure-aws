## Using Terraform Modular Structure for AWS
Terraform is a popular infrastructure as code (IaC) tool that allows you to provision, manage, and version control cloud infrastructure. In this guide, we'll explore how to use Terraform's modular structure to manage AWS infrastructure.

### Prerequisites
- A basic understanding of Terraform
- An AWS account
- Terraform installed on your local machine

### Modules created for this Infrastructure
Two modules are created in this example and will be created after executing this code:
- Subnet Module (includes Internet Gateway, Subnet and Route Tables)
- Webserver (includes Security Group, fetching latest Amazon Linux Image, ssh key pair and EC2 instance)
- EC2 server will be initialised with `entry-script.sh`

## Basic Commands for Terraform

### Initialize project in directory

    terraform init

### Preview terraform actions

    terraform plan

### Apply configuration with variables

    terraform apply -var-file terraform-dev.tfvars

### Destroy a single resource

    terraform destroy -target aws_vpc.myapp-vpc

### Destroy everything from .tf files

    terraform destroy

### Show resources and components from current state

    terraform state list

### Show current state of a specific resource/data

    terraform state show aws_vpc.myapp-vpc    

### Set avail_zone as custom tf environment variable - before apply

    export TF_VAR_avail_zone="eu-west-3a"