<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-security)

**Author:** James Paonessa  
**Email:** james@jamespaonessa.com

---

## VPC Traffic Flow and Security

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a private virtual network in AWS that allows you to securely run cloud resources in an isolated environment. It is useful because it gives you control over networking, subnets, routing, internet access, and security boundaries, similar to designing a traditional network but in the cloud.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to build out our own internal cloud network complete with its own subnet, security group and ACL's.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the creation of default ACL's and security groups in the process of creating prior portions of this project. In future instances I would reuse/automate the creation of these pieces at the start to reduce clutter.

### This project took me...

This project took me roughly 30-40 minutes, with the creation of this documentation included.

---

## Route tables

Route tables are tables of rules that decide where our network traffic should go.


Routes tables are needed to make a subnet public because we need to specify how to direct our internet traggic in and out of our subnet.

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Routes are defined by their destination and target, which reference where we want our traffic to reach and the route it will take.

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0, translating to all IPv4 addresses and a target of 10.0.0.0/16, which includes all traffic that is not bound for another VPC/instance. This becomes a catch-all for internet traffic.

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are a specific set of rules that are applied to the way traffic can move in these instances. 

### Inbound vs Outbound rules

Inbound rules are applied to traffic coming in. I created rules allow HTTP and HTTPS traffic in on ports 80/443.

Outbound rules are applied to traffic leaving VPC/Subnet. By default, my security group's outbound rule allows all traffic to exit.

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs are a set of traffic rules that apply to the entire subnet.

### Security groups vs. network ACLs

The difference between a security group and a network ACL is that ACL's sit in front of the subnet and in turn the security groups that govern them. The ACL's are the broad set of rules vs security groups are the fine tuning.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will allow any traffic, but as soon as we create a set of rules, it becomes a deny by default situation.

By putting in our custom ACL’s inbound and outbound rules, we become a deny-by-default ruleset and can fine-tune by adding specific Allow rules.

![Image](http://learn.nextwork.org/gleeful_brown_zany_hog/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

---

---
