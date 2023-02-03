# EC2

- EC2 is one of most popular of AWS's offering.
- EC2 stands for Elastic Compute Cloud = Infrastructure as a service.
- It mainly consists in the capability of:
  - Renting virtual machines (EC2)
  - Storing data on virtual drives (EBS)
  - Distributing load across machines (ELB)
  - Scaling the services using an auto-scaling group (ASG)
- Knowing EC2 is fundamental to understand how the cloud works.

It's no limit that you want to rent a virtual machine on the cloud based on what you need and configure

- Operating System (OS)
- How much compute power & core (CPU)
- How much random-access memory (RAM)
- How much storage space:
  - Network-attached (EBS & EFS)
  - Hardware (EC2 instance store)
- Network card: speed of the card, Public IP address
- Firewall rules: security group
- Bootstrap script (configure at first launch): EC2 User Data

## EC2 User data

- We can use it to bootstrap our instances by EC2 User data script (launching commands when a machine starts).
- It will run once at the instance first start and never re-run again.
- It is used to automate boot tasks such as:
  - Installing updates
  - Installing software
  - Downloading common files from the internet
  - ...

## Important

- The EC2 user data script runs with the root user -> any commands will have the pseudo rights.
- `T2.micro` instance is part of AWS free tier (up to 750 hours per month)
