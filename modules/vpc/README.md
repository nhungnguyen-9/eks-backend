# 🧠 VPC Infrastructure Diagram with Terraform

## 🏗 Key Components:
- **VPC**: A virtual network in AWS that houses all infrastructure.

- **Public Subnet**:

- Has a route to the Internet through an Internet Gateway (IGW).

- EC2 instances in this subnet can access and be accessed from the Internet.

- **Private Subnet**:

- Routes to the Internet through a NAT Gateway (located in the Public Subnet).

- EC2 instances in this subnet can access the Internet but do not receive inbound traffic from it.

- **Route Table (RT)**: A routing table that defines the routes for each subnet.

- **IGW**: The gateway connecting the VPC to the Internet.

- **NAT Gateway**: Allows private subnets to access the Internet while maintaining security.

## Network Flow:

Public Subnet → RT → IGW → Internet

Private Subnet → RT → NAT → IGW → Internet

## 🛠 Terraform will create:
- VPC

- 2 types of Subnets: Public & Private

- Route Tables for each type

- IGW and NAT Gateway

- Attach route tables to each subnet

![vpc](vpc-tf.png)