# VPC

Virtual Private Cloud - (Only private IP are allowed because VPC is private)

- You can have multiple VPCs in an AWS region (max 5 per region - soft limit => we can increase it)
- Max CIDR per VPC is 5, for each CIDR:
  - Min size is /28 (16 IP addresses)
  - Max size is /16 (65536 IP addresses)
- Private IPv4 ranges are allowed:
  - 10.0.0.0 - 10.255.255.255 (10.0.0.0/8)
  - 172.16.0.0 - 172.16.255.255 (172.16.0.0/12)
  - 192.168.0.0 - 192.168.255.255 (192.168.0.0/16)
- Our VPC CIDR should not overlap with the other networks.

- All the new AWS accounts have a default VPC.
- New EC2 instances are launched into the default VPC if no subnet is specified.
- Default VPC has Internet connectivity and all EC2 instances inside it have public IPv4 addresses. => We can able to connect to our EC2 instances right away when we created them.
- We also get a public and a private IPv4 DNS names.
