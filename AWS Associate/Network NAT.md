# NAT Instance **outdated**

- NAT = Network Address Translation
- Allow EC2 instances in private subnets to connect to the internet.
- Must be launched in a public subnet.
- Must disable EC2 setting: **Source/destination Check**
- Must have Elastic IP attach to it.
- Route tables must be configured to route traffic from private subnets to the NAT instance.

Notes:

- Pre-configured Amazon Linux AMI is available.
  - Reached the end of standard support on December 31, 2020
- Not highly available / resilient setup out of the box.
  - We need to create an ASG in multiple AZ + resilient user-data script.
- Internet traffic bandwidth depended on EC2 instance type.
- We must manage Security Group & rules:
  - Inbound:
    - Allow HTTP/HTTPS traffic comming from Private Subnets.
    - Allow SSH from your home network (access is provided throw Internet Gateway)
  - Outbound:
    - Allow HTTP/HTTPS traffic to the internet.
