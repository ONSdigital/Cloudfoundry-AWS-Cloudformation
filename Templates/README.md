# Templates

These AWS templates are to be used by the main templates, eg through the use of AWS::CloudFormation::Stack

- External-Access-Whitelist.json
  - Add provided CIDR to the provided security groups, currently CfSshSecurityGroup, DirectorSecurityGroup & LbSecurityGroup.  This will whitelist the CIDR for specific ports within each of the security groups
