## Disaster Recovery Plans (ordered by cost ascending)

- **Backup and Restore:** Self-describing. Require to launch new instances of everything and load the backups.
- **Pilot Light:** Storing critical systems as template from which resources can be scaled out.
- **Warm Standby:** A smaller, duplicated version of business critical systems always running.
- **Multi-site:** An entire duplicate of the system in a different location (physical or virtual).
## VPC

- **Virtal Private Cloud**. It's your own "piece" of the AWS cloud. 
- Can span multiple AZs in a single region and contain multiple public and private subnets.
- Contains its own CIDR range, in case there are overlapping VPC connections, a NAT is required to correctly map requests.
- **Public subnet:** Has access to the internet (i.e. Contains a route to the internet gateway).
- **Private subnet:** AWS resources access only (no internet access). A NAT gateway or instance in a public subnet is required to provide internet access to a private subnet.
-  If you need SSH access from the internet to a resource in a private subnet you need to set up a bastion host on a public subnet and configure your Security Groups and Network Access Control Lists accordingly for forwarding traffic on port 22.
## Route Tables

- Rules how traffic can flow within your VPC.
- Always contains a destination and a target, e.g. `0.0.0.0/0` (CIDR Destination) and `igw-1234567890`. The CIDR block contains all IPv4 addresses of the subnet and points them to the Internet Gateway.
- Usually the target is the "vehicle" that will lead your service to the destination.
- Attached to certain subnets.
- There is a default route table (main route table) which will be associated with each newly created subnet as long as you don’t attach one by yourself.
- The main route table can’t be deleted.
- You can add, modify, and remove routes in this table.
- One subnet can only have one route table.
- The same route table can be attached to multiple subnets.
- Route tables can also be attached to your Virtual Private Gateway or Internet Gateway so you can define how traffic entering your VPC will be routed.
- Your VPC always has an implicit router to which your route tables will be attached to.

## Virtual Private Gateway (VPC Gateway)

- Component on the AWS side that allows VPCs to receive multiple VPN connections.
- Needed if you want to connect your AWS VPC with an on-premise Network.
- 1.25 gbps throughput limit.

## Network Access Control List (NACLs)

- Operating on the **subnet level** and are **stateless**.
- They can define **block & allow rules**.
- By default allow traffic for all ports in both directions.
- Return traffic must be explicitly allowed.

## Security Groups (SGs)

- Operating on the **instance level** and are **stateful**.
- They only define **only allow rules**.
- The default security group allows communication of components within the security group, **allow all outgoing traffic** and **block all incoming traffic**.
- Return traffic is implicitly allowed (opposite to NACLs).
- SGs can be attached or removed from EC2 instances at any time (state of machine does not need to be stopped or terminated).
- Rules always need to specify CIDR ranges and never a single IP.
- If you want to have a dedicated IP, e.g. `10.20.30.40` you also need to define it as a CIDR range covering only a single IP by its subnet mask: `10.20.30.40/32` .

## CIDR (Classless Inter-Domain Routing)

- Certain range of IP-Addresses.
- The first four IP addresses and the last IP address in each CIDR block are not available for you to use, and cannot be assigned to an instance.
- Important to know how they are built, because they are used in different touch points, e.g. SGs.

## VPC Endpoints

- Needed to access AWS Services which are not part of your VPC.
- Traffic between VPC and other services does not ever leave Amazon Network.
- There are different types.
- **Gateway Endpoint** — A gateway that is a target for a specified route in your route table (S3, Dynamo).
- **Interface Endpoint** — An Elastic Network Interface (ENI) with a private IP address that serves as an entry point (use it for CloudFormation, CloudWatch, etc.). Are powered by AWS PrivateLink.

## NAT Gateway & Instance

- Needed to connect private resources to public internet or other AWS resources without exposing their private IP address.
- There are two different types.
- **NAT Instance** — managed by the user with no default auto-scaling.
- **NAT Gateway** — AWS Managed, scales based on demand, fewer administrations required, and higher availability compared to the NAT Instance.
## VPC Peering

- Connecting different VPCs.
- Also possible to connect with VPCs of other accounts.
- CIDR-ranges **should not overlap**.
- Connections are **not transitive**, therefore `A ← Peering → B ← Peering → C` means that there is **no connection** between A and C.
- You can not edit a peering connection once it has been stablished.
- Can not attach or detach VPC peering connections.

## VPC Flow Logs

- Details about the IP traffic to and from network interfaces in a VPC. User can setup a flow log for specific services and decide whether to record accepted, rejected or all traffic.
- Data is stored **not in real time** in S3 or as CloudWatch logs.
- Once a flow log is created, its configuration can not be changed. 
- Flow logs can not be enabled in VPCs with a peering connection unless both VPCs are in the same account.
- The actual content of IP packets is not recorded on Flow Logs.

## Transit Gateway

- Hub to connect multiple resources through distinct peering relationships (VPN, Direct Connect, VPC Peering, etc.).

## Elastic IP Addresses (EIPs)

- Can be moved from one instance to another within multiple VPCs in the same region.

## Elastic Network Interface (ENI)

- Attach multiple IP addresses to the same instance.

## Elastic Network Adapter (ENA)

- Enhcance the network capabilities of your instances.
- Allows you to fully take advantage of bandwith on distributed network workloads.
- Enables IP packages to skip going through the CPU and directly delivered to the application.

