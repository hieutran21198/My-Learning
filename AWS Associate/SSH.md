# SSH

- SSH is one of the most important function. It allows you to control a remote machine, all using the command line.

## How to SSH into your EC2 instance using Linux/Mac

- Download the PEM file.
- Go to the EC2 instance and get the Ipv4/Ipv6 public address.

```bash
chmod 0400 ./EC2Helloworld.pem
ssh -i EC2Helloworld.pem ec2-user@192.168.1.1
```

- `EC2Helloworld.pem` is the PEM file.
- `ec2-user` is the Amazon Linux 2 AMI. (default user)
- `192.168.1.1` is the public IP of our EC2 instance.

## Important

- We can use the EC2 Instance connect as the alternative method.
- Never provide AWS access key ID, Secret access key into an EC2 instance. Because the others have permissions to connect EC2 instance can see it as well. Instead, what we have to do is use the `IAM rules` with `IAMReadOnlyAccess` policy and use `aws iam list-users` command.
