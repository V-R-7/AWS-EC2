# Security Groups

When we create an instance, we must configure a Security Group.
- Security Groups acts as virtual firewall to the AWS EC2 Instances.
- They manage inbound and outbound network traffic to your instances.

A security group acts as a virtual firewall for your instance to control inbound and outbound traffic.
It allows traffic which you specify others are blocked.

To summarize :
- They are instance level firewall which allows users to restrict the incoming and outgoing traffic by specifying the traffic which are allowed.
  
By default, the port (22) SSH is configured.
We may also allow other common ports like HTTP (80), HTTPS (443), RDP (3389)

## Default Traffic by Security Group
- No inbound traffic is allowed.
- Outbound traffic is allowed.

##  Inbound and Outbound Rules
You define rules which are inbound and outbound.

![EC2 Security Group](https://github.com/V-R-7/AWS-EC2/assets/62888693/3561177b-d4e5-4c0b-a308-4b047a7fd6cb)

## Logging 

Whenever there are Security group changes being done and rule changes done, they are logged in the Amazon CloudTrail service.

## Authorize IPv4 & IPv6

We can regualate authorizing IPv4 and IPv6 using Security group, by defining inbound and outbound rules for both IP address families.
It is IP protocol agnostic and we can use the same security group to control both IPv4 and IPv6 traffic.

Set specific inbound and outbound rules for both the IP Protocols & save it.

Remember:
- The Source IP 0.0.0.0/0 allows traffic from any IPv4 address.
- The Source IP ::/0 allows traffic from any IPv6 address.

Adjust rules based on specific requirements.

Configure your security groups carefully to allow only neccessary traffic, and also ensure to review the security group and update it to maintain it securely. 

