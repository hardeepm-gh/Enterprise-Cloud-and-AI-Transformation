Terraform Journey: Day 17
Project: AWS Networking & RDS Provisioning
✅ Accomplishments
VPC Infrastructure: Created a custom VPC with public subnets, internet gateway, and DNS hostnames enabled.
Database Provisioning: Successfully deployed an AWS RDS PostgreSQL instance using Terraform.
Network Security: Configured Security Groups to handle dual-stack (IPv4 and IPv6) ingress for local machine access.
Subnet Management: Created a custom aws_db_subnet_group to force database placement into public-facing subnets.
Connection Verified: Confirmed end-to-end connectivity using nc (netcat) and psql client.
🛠️ Challenges Overcome
DNS Resolution (NXDOMAIN): Fixed by enabling enable_dns_hostnames in the VPC module.
Public Routing: Solved the connectivity timeout by ensuring the RDS was in a subnet with a route to the Internet Gateway.
IPv6 Rotation: Addressed the "Temporary IPv6" issue by whitelisting a /64 network range rather than a single static IP.
Bracket Mismatch: Debugged HCL syntax errors regarding egress and lifecycle blocks.
📊 Infrastructure Overview
ResourcePurposemodule.vpcBase network (10.0.0.0/16)aws_db_instancePostgreSQL 15 engine on db.t3.microaws_security_groupPort 5432 whitelist for local IPaws_db_subnet_groupBridges RDS to the Public Subnets
