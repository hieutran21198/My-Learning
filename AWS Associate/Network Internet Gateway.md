# Internet Gateway (IGW)

- Allows resources (eg., EC2 instances) in a VPC connect to the internet.
- It scales horizontally and is highly available and redundant.
- Must be created separately from a VPC.
- One VPC can only attached to one `IGW` and vice versa.

Notes:

- `IGW` on their own do not allow internet access. We **must** also edit the `Route Tables` to make it work.

<img src="./Assets/Images/IGW.png" alt="Internet gateway" />
