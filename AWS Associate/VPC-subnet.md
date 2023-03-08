# Subnet

- It is a sub range of IPv4 addresses within our VPC.
- AWS reserves 5 IP addresses (first 4 and last 1) in each subnet.
- These 5 IP addresses are not available for use and can't be assigned to an EC2 instance:
  - If CIDR block 10.0.0.0/24, then reserved IP addresses are:
    - 10.0.0.0 - Network address.
    - 10.0.0.1 - reserved by AWS for the VPC router.
    - 10.0.0.1 - reserved by AWS for mapping to Amazon-provided DNS. (important)
    - 10.0.0.3 - reserved by AWS for future use.
    - 10.0.0.255 - Network broadcast address. AWS does not support broadcast in a VPC, therefore the address is reserved.

Note: If you need 29 IP addresses for EC2 instances:

- You can't choose a subnet of size /27 (32 - 5 = 27 => 2^6 IP addresses available) (32 IP addresses, 32 - 5 = 27 < 29)
- You need to choose the subnet of size /26 (32 - 6 = 26 => 2^6 IP addresses available) (64 IP addresses, 64 - 5 = 59 > 29)
