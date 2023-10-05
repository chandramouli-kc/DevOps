https://www.bdrsuite.com/blog/amazon-ec2-mac-instances-how-to-create/

===============Complete VPC through Terraform=================
https://medium.com/@aliatakan/terraform-create-a-vpc-subnets-and-more-6ef43f0bf4c1
https://spacelift.io/blog/terraform-aws-vpc


# DevOps
DevOps Projects
# First line added
# added second line
provider "aws" {
    region = "ap-south-1"
}

 #  Dev VPC CIDR Creation

 VPC
 =============
provider "aws" {
    region = "ap-south-1"
}

 #  Dev VPC CIDR Creation 
resource "aws_vpc" "dev" {
  cidr_block = "${var.vpc_cidr}"
  instance_tenancy = "${var.tenency}"

  tags = {
    Name = "dev"
  }
}


# Subnet Dev Public 
resource "aws_subnet" "dev-public" {
  vpc_id     = "${var.vpc_id}"
  cidr_block = "${var.subnet_cidr}"
 
  tags = {
    Name = "dev-public"
  }
}




==============Vars

variable "vpc_cidr" {
    default = "10.0.0.0/16"
}

variable "tenency" {
    default = "dedicated"
}


===============EC2



provider "aws" {
   region     = "ap-south-1"
   access_key = "AKIA5BZOXENAX7VE3MVG"
   secret_key = "cDYy+Exm2jeanG31l/4Kl7hqR4DIS5w8/J4wboOU"
}

resource "aws_instance" "ec2_example" {
   
   ami           = "ami-0756a1c858554433e"
   instance_type = var.instance_type
   
   tags = {
           Name = "Terraform EC2-String"
   }
}

variable "instance_type" {
   description = "Instance type t2.micro"
   type        = string
   default     = "t2.nano"
}


