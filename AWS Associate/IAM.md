# IAM

## User & Group

- IAM equals Identity and Access Management, Global Service.
- Users are people within your organization, can be grouped.
- User don't have to belong to a group and user can belong to groups.

<img src="./Assets/Images/IAM/group-of-users.png" alt="Group of users" />

## Permissions

- User or Groups can be assigned JSON documents called policies.
- These policies define the permissions of the user.

## IAM Policies inheritance

<img src="./Assets/Images/IAM/policies-inheritance.png" alt="Policies inheritance" />

Example:

```json
{
  "version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:Describe*",
      "Resource:": "*"
    },
    {
      "Effect": "Allow",
      "Action": "elasticloadbalancing:Describe*",
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": [
        "cloudwatch:ListMetrics",
        "cloudwatch:GetMetricStatistics",
        "cloudwatch:Describe*"
      ],
      "Resource": "*"
    }
  ]
}
```

## Important

- Root account created by default, shouldn't be used or shared.

- In `AWS` you apply the `least privilege principle`: don't give more permissions than a user needs.
