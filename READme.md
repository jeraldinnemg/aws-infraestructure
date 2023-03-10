## Infrastructure as Code with Terraform

### Real-world infrastructure deployment

This is a medium difficulty mandatory activity, which aims to build a more robust, secure, and resilient cloud infrastructure consisting of the following resources:

- A VPC.
- An Internet Gateway associated with the created VPC.
- A public subnet.
- A private subnet.
- A routing table dedicated to the public subnet.
- A routing table dedicated to the private subnet.
- Associations of both routing tables with their respective subnets.
- A NAT Gateway associated with the private subnet.
- An Elastic IP.

The code will be modularized, segmented into three files: one for variables, another to select the Cloud provider, and the last one that will be used to deploy the infrastructure. The infrastructure will look like this:

![](images/vpc-aws.png)

Although, for practical reasons, we will focus only on the infrastructure and not the services that will be deployed within it.

### Directory and Modules Structure

To make each Terraform module we will use work, we must place them all in the same directory. The files will be named:

- `main.tf` (will be used to deploy the entire infrastructure of my VPC).
- `variables.tf` (will contain the variables that I want to pass to each module).
- `providers.tf` (will be used to define which Cloud provider and versions to use).

When we run `terraform init`, the first thing that will happen is the reading of the module, `providers.tf`, where it will search for which Cloud provider to use. Then, the order is alphabetical, that is, it will execute module by module according to the initial name of the file or module.

### Documentation

Please keep the Terraform documentation at hand since we will be consulting it as we go along.

- [Terraform Documentacion](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)

Let's get started!

### Resources deployed in AWS

#### Resources deployed using `terraform` in Ubuntu VM.
![](images/terraform-apply.png)

#### Resources created in AWS
![](images/demo-aws-vpc.png)
![](images/subnets.png)
![](images/IGT.png)
![](images/nat.png)
![](images/elastic-ip.png)
![](images/secruity-groups.png)



