# Misc AWS Cloudformation Templates

1. VPC Peering
   - AWS-VPC-Cross-Account-Role-template.json
     - Destination peering account VPC peering role
   - AWS-VPC-Peering-Routing.json
     - Destination peering account VPC routing
   - AWS-VPC-Peering.jsonA
     - Example of VPC peering

2. Replicate Buckets
   - AWS-Versioned-Replicated-Backup-S3-001.json
     - Versioned & replicated S3 backup bucket: replica bucket - to be added to destination region. **This template should be loaded first**
   - AWS-Versioned-Replicated-Backup-S3-002.json
     - Versioned & replicated S3 backup bucket: source bucket and replication configuration - to be added to source region. **This template should be loaded after the replca bucket has been created**
