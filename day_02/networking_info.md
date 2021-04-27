### Virtual Private Cloud (VPC)
Allows you to define and control a virtual network

(According to AWS) Allows you to launch AWS resources into a virtual network that you've defined. This virtual network closely resembles a traditional network that you'd operate in your data center. 

### Benefits to VPCs
- Allows the EC2 instances to communicate with each other
- Can create different subnets within the VPC
- It gives us scalability of infrastructure

### Internet gateways
- Allows your subnets to connect to the internet
- A gateway that you attach to your VPC to enable communication between

### Subnets
- These are networks that sit within a VPC. They make networks more efficient(?)
- They are a range of ip addresses in a VPC
- A subnet can have multiple EC2 instances

### Route tables
- Used to let a devices know where to find certain ips.
- A set of rules, called routes

### (N) ACLs
- An added layer of security. They work at the network (subnet) level. 
- (N) ACLs are stateless - because you need rules to allow the requests in and the response out

### Security groups
- They work as a firewall on an instance level. They are attached to the VPC and subnet
- We can define unbound and outbound traffic rules
- They are stateful - this means that returning traffic can ... (I missed this)

### Ephemeral/dynamic ports
- They are shortly lived ports that are automatically allocated based on demand
- Allows outbound responses to clients on the internet
- They range from 1024-65535