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

Example: `T2.micro` instance is part of AWS free tier (up to 750 hours per month)

## EC2 user data

- We can use it to bootstrap our instances by EC2 User data script (launching commands when a machine starts).
- It will run once at the instance first start and never re-run again.
- It is used to automate boot tasks such as:
  - Installing updates
  - Installing software
  - Downloading common files from the internet
  - ...

## EC2 instance types

- Detail about EC2 instance located [here](https://aws.amazon.com/ec2/instance-types/).
- AWS has the following naming convention:<br>

  [instance_class][generation (aws improves them over time)].[size within the instance class]<br>

  For example: m5.x2large

- Now we have 7 different types for any purposes.

### EC2 instance types - General purpose

- Great for diversity of workloads such as web servers or code repositories
- Balance between:
  - Compute
  - Memory
  - Networking

### EC2 instance types - Compute optimized

- Great for compute-intensive tasks that require high performance processors:
  - Batch processing workloads
  - Media transcoding
  - High performance web servers
  - High performance computing (HPC)
  - Scientific modeling & machine learning
  - Dedicated gaming servers

### EC2 instance types - Memory optimized

- Great for workloads that process large data sets in memory
- Use cases:
  - High performance, relational/non-relational databases.
  - Distributed web scale cache stores.
  - In-memory databases optimized for BI (business intelligence).
  - Applications performing real-time processing of big unstructured data.

### EC2 instance types - Storage optimized

- Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage.
- Use cases:
  - High frequency online transaction processing (OLTP) systems.
  - Relational & NoSQL databases.
  - Cache for in-memory databases. (for example: Redis)
  - Data warehousing applications.
  - Distributed file systems.

## Important

- The EC2 user data script runs with the root user -> any commands will have the pseudo rights.
