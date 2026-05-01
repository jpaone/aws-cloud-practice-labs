<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** James Paonessa  
**Portfolio:** AWS Infrastructure Practice Lab  
**Contact:** Available via GitHub or LinkedIn

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate the setup and useage of Amazon VPC. I'm doing this project to continue my learning path of Amazon Cloud and how to connect instances and there contents.

### What is Amazon VPC?

Amazon VPC is the control mechanism to set up your own internal networking system for you instances and resources used within the AWS system. This is useful for connecting these resources within the AWS system like a traditional network.

Today we used Amazon VPC to make a simple network with its own subnet. This could in theory be used to provide resources available to the public at large and seperate resources for internal useage.

### Personal reflection

This project took roughly 30 mins.

One thing I did not realize was that AWS was creating a simplified version of this system when I was creating instances. I knew prior that manual creation would be needed but not that AWS was semi-automatically doing this also.

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will be setting up and defining the parameters of my VPC. This is necessary to build the foundational framework for my internal network and how it relates to projects.

### How VPCs work

VPCs (Virtual Private Clouds) are a segmented, private network within the larger cloud ecosystem.

### Why there is a default VPC in AWS accounts

There was already a default VPC in my account ever since my AWS account was created. This is because AWS sets this initial infrastructure point so our initial projects (before configuration) are connected to the AWS infrastructure right away.

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is the way of writing out how we want the VPC to set up its IP address scheme.

---

## Subnets

### What I did in this step

In this step, I will be setting up a subnet within my VPC. This will allow me to segment addresses, creating "groups" which the devices/VMs/end-points can utilize.

### Creating and configuring subnets

Subnets are groups of resources or IP addresses. There are already subnets existing in my account, one for every predefined region.

### Public vs private subnets

The difference between public and private subnets is whether they have direct access to the internet. I have not yet added a gateway to this subnet, allowing it access to the internet

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled "auto-assign public IPv4 addresses". This setting makes sure that any instances on our subnet will be assigned a NAT routable IP address and conflicts do not occur.

---

## Internet gateways

### What I did in this step

In this step, I will be adding an Internet Gateway because my current VPC and subnet has networking addresses but does not have access to the global internet yet.

### Setting up internet gateways

Internet gateways are the actual link between our VPC and the global internet.

Attaching an internet gateway to a VPC means that I have designated this internet gateway to act as the default route for this VPC.
If I missed this step, the VPC would still have no route out to the internet at large and would still be contained.

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will be utilizing AWS CloudShell to run the CLI commands to setup a VPC, subnet and Internet Gateway. This gives added flexibility to complete this process through an Infrastructure as Code or Network as Code method of completing tasks.

### Exploring CloudShell and CLI

VPC resources could also be created with CloudShell, which is the command-line method of creating resources.

### Debugging my setup

To set up a VPC or a subnet, you can use the command 
aws ec2 create-subnet --vpc-id  --cidr-block 
Make sure to avoid errors by including the name of your VPC in the argument --vpc-id and your cidr block information in the arugment --cidr-block.

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

CloudShell was unavailable because the AWS account was still pending verification, so I completed the same AWS CLI workflow from macOS Terminal. The commands are functionally the same as the CloudShell tutorial, but I used shell variables such as $VPC_ID, $SUBNET_ID, and $IG_ID to store resource IDs and reuse them in later commands.

---

---
