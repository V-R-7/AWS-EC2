# Security Groups

When we create an instance, we must configure a Security Group.
- Security Groups acts as virtual firewall to the AWS EC2 Instances.
- They manage inbound and outbound network traffic to your instances.

A security group acts as a virtual firewall for your instance to control inbound and outbound traffic.
It allows traffic which you specify others are blocked.

By default, the port (22) SSH is configured.
We may also allow other common ports like HTTP (80), HTTPS (443), RDP (3389)

## Default Traffic by Security Group
- No inbound traffic is allowed.
- Outbound traffic is allowed.

##  Inbound and Outbound Rules
You define rules which are inbound and outbound.

![EC2 Security Group](https://github.com/V-R-7/AWS-EC2/assets/62888693/3561177b-d4e5-4c0b-a308-4b047a7fd6cb)
