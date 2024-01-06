# Disaster Recovery Plans (ordered by cost ascending)
- **Backup and Restore:** Self-describing. Require to launch new instances of everything and load the backups.
- **Pilot Light:** Storing critical systems as template from which resources can be scaled out.
- **Warm Standby:** A smaller, duplicated version of business critical systems always running.
- **Multi-site:** An entire duplicate of the system in a different location (physical or virtual).
# VPC
- Virtal Private Cloud. It's your own "piece" of the AWS cloud. 
- Can span multiple AZs in a single region and contain multiple public and private subnets.
- Contains its own CIDR range, in case there are overlapping VPC connections, a NAT is required to correctly map requests.
- **Public subnet:** Has access to the internet (i.e. Contains a route to the internet gateway).
- **Private subnet:** AWS resources access only (no internet access). A NAT gateway or instance in a public subnet is required to provide internet access to a private subnet.
-  If you need SSH access from the internet to a resource in a private subnet you need to set up a bastion host on a public subnet and configure your Security Groups and Network Access Control Lists accordingly for forwarding traffic on port 22.
# Route Tables
