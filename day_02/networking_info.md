### Virtual Private Cloud (VPC)
These work like a firewall  
Allows you to provision an isolated section of the cloud for resources. This 'section' is a virtual network.  
Allows you to launch AWS resources into a virtual network that you've defined. This virtual network closely resembles a traditional network that you'd operate in your data center.  

### Benefits to VPCs
- Allows the EC2 instances to communicate with each other
- Can create different subnets within the VPC
- It gives us scalability of infrastructure

### Internet gateways
- Allows your subnets to connect to the internet
- A gateway that you attach to your VPC to enable communication between subnets and the internet

### Subnets
- These are networks that sit within a VPC. They make networks more efficient(?)
- They are a range of ip addresses in a VPC
- A subnet can have multiple EC2 instances

### Route tables
- Used to let a devices know where to find certain ips.
- A set of rules, called routes

### (N) ACLs
- An added layer of security. They work at the network (subnet) level. 
- They can be used to control the access between subnets _within_ a VPC
- (N) ACLs are stateless - because you need rules to allow the requests in and the response out

***Public ACL***
Inbound Rules
- 100 Allows inbound HTTP traffic from any IPv4 address 
- 110 Allows inbound SSH traffic from your network over the Internet
- 120 Allows inbound return traffic from hosts on the Internet that are responding to requests from the subnet - TCP 1024 - 65535

Outbound rules
- 100 Allows port 80
- 110 for port 27017 and outbound access to our database server using CIDR block
- 120 to allow short lived ports between 1024 - 65535

***Private ACL***
Inbound Rules


Outbound Rules


### Security groups
- They work as a firewall on an instance level. They are attached to the VPC and subnet
- We can define unbound and outbound traffic rules
- They are stateful - this means that returning traffic can ... (I missed this)

(for the app)
Inbound rules
- Create a security group for the app
- Allow port 80 to all
- Allow port 22 for ssh

Oubound rules
- Allow all

(for the private sg)
- Create a security group for the database
- Allow access from the app security group (27017???)

### Ephemeral/dynamic ports
- They are shortly lived ports that are automatically allocated based on demand
- Allows outbound responses to clients on the internet
- They range from 1024-65535


### Task Work
When I spind up EC2 from ami, spin them up in default vpc to make sure posts works
