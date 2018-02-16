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

3. RDS Snapshot User
   - AWS-RDS-Snapshot-User.json
     - Creates an AWS user & group that have permission to snapshot a predefined database, list snapshots for that database and delete specific snapshots that have the database name as their prefix

# RDS Snapshot Instructions

To create an RDS snapshot:

`aws rds-create-db-snapshot--db-instance-identifier my-database --db-snapshot-identifier my-database-snapshot-identifier`

Only snapshots that have the format of $DATABASE\_NAME-$IDENTIFIER" can be created. $IDENTIFIER can be any alphanumeric string, including hypens.


To list the snapshots for an RDS instance:

`aws rds describe-db-snapshots --db-instance-identifier my-database`

All snapshots can be listed.


To delete an RDS snapshot:

`aws rds delete-db-snapshot --db-snapshot-identifier my-database-snapshot-identifier`

Only snapshots that have the format of $DATABASE\_NAME-$IDENTIFIER" can be delete, $IDENTIFIER can be any alphanumeric string, including hypens.
