# AWS Cloudformation Templates

These templates create an the AWS infrastructure required to build a single or multi AZ Cloudfoundry installation.

Most of the templates take various parameters to control what parts of the infrastructure are created.  The defaults should work out of the box.

- AWS-Bosh-preamble.json:
  - This creates an S3 bucket. This is used to allow templates bigger than the AWS inline template size limit of 51,200 bytes. See http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cloudformation-limits.html.

- AWS-Bosh-000-Common.json
  - This contains a common set of parameters and outputs.  It also adds stack protection against updates and/or deletions.

- AWS-Bosh-001-EIP.json
  - This creates the required number of AWS Elastic IPs.

- AWS-Bosh-002-VPC.json
  - This creates the base VPC

- AWS-Bosh-003-SecurityGroups.json
  - This creates the common set of security groups

- AWS-Bosh-004-DMZ.json
  - This creates the various DMZ network(s).  This is used by either the AWS Elastic Load Balancer, or the internal Cloudfoundry load balancer

- AWS-Bosh-005-Nat.json
  - This creates the various NAT gateway(s).  Most of the networks reach out to the Internet using one of these NAT gateways.  Currently one per AZ

- AWS-Bosh-006-Director.json
  - This creates the network(s) that holds the Bosh Director.  It supports multiple AZs, even if the Bosh Director doesn't

- AWS-Bosh-007-Private.json
  - This creates the internal network(s) where the majority of the Cloudfoundry instances live

- AWS-Bosh-008-ELB.json
  - This, optionally, creates Elastic Load Balancers for the Director, Cloudfoundry SSH (eg cf ssh) and/or the external facing load balancer

- AWS-Bosh-009-DNS.json
  - This adds the Route53 DNS entries for various parts of the system

- AWS-Bosh-010-S3.json
  - This creates a range of S3 buckets for use by Cloudfoundry/Bosh

- AWS-Bosh-011-VPC-Peering.json
  - This creates peering between 0-4 different AWS accounts

- AWS-Bosh-012-VPC-Endpoints.json
  - This adds VPC endpoints for S3 access

- AWS-Bosh-013-Users.json
  - This creates the user that Bosh/Director uses to create the Cloudfoundry instances

- AWS-Bosh-014-Whitelist.json
  - This adds the various IPs (eg HTTP access, FULL access) to specific security groups to allow platform access

- AWS-Bosh-101-ElastiCache.json
  - This, optionally, creates the infrastructure for ElastiCache

- AWS-Bosh-102-RabbitMQ.json
  - This, optionally, creates the infrastructure for RabbitMQ

- AWS-Bosh-103-RDS.json
  - This, optionally, creates the infrastructure for the RDS instances and create the Cloudfoundry internal RDS instance and/or the Cloudfoundry applications RDS instance

- AWS-Bosh-200-RouteTableAssociations.json
  - This associates the various routes and route tables

- AWS-Bosh-201-Ingress.json
  - Inter subnet/network/security group ingress rules

- AWS-Bosh-202-Egress.json
  - Inter subnet/network/security group egress rules
