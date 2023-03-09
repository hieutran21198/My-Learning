# Bastion Hosts

<img src="./Assets/Images/BastionHost.png" alt ="bastion host"/>

- It's an EC2 instance in a public subnet.
- We also have a bastion hosts security group.
- We can use a bastion host to SSH into our private EC2 instances.
- The bastion is in the public subnet which is then connected to all other private subnets.
- **Bastion Host security group must allow** inbound from the internet on port 22 from restricted CIDR.
- We have to restrict the EC2 security group of the bastion host as much as possible to guarantee that only a few IPs can access them.
- Security group of the EC2 instances must allow the security group of the Bastion Host, or the private IP of the bastion host.

## Recommended steps to link new bastion host and new private EC2 instance:

- Create a new `Key Pairs` in EC2. (PEM)
- Launch a new private EC2 instance:
  - Select the created key pair.
  - Select the VPC and private subnet of this VPC that you want to connect.
  - Create a new private security group.
  - Create a new inbound security group rule, with the `custom source` linked to some EC2 instances.
- Connect Bastion Host EC2 instance.
  - Use this command to connect to the private EC2 instance `ssh ec2-user@${PRIVATE_EC2_INSTANCE_IP}` for the first time.
  - We will need to specify a key pair. Example: paste the content of the previous `pem` file to the `Bastion Host` instance. Example: `vi PEC2KeyPair.pem && chmod 0400 ./PEC2KeyPair.pem`
  - Use this command to connect to the private EC2 instance if you already setup the new `pem` file in `Bastion Host` instance `ssh ec2-user@${PRIVATE_EC2_INSTANCE_IP} -i ./PEC2KeyPair.pem`.
