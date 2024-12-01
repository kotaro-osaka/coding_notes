# Security Services
___
## IAM
*Identity and Access Management*
### User
- No permissions by default
- Associate IAM Policy to grant/deny permissions
### Group
- Group users
- Manage users
- Attach policies to apply rules to multiple users
### Policy
- JSON document
- Specifies API calls a user is allowed to use
### Role
- Associated permissions
- Assumed for temp amounts of time
- On assumption of a role, previous permissions are abandoned
#### Use Cases
- AWS resources
- Users
- External identities
- Apps
- Other AWS services
___
## Organization
- Centralized management of AWS accounts
- Consolidated Billing
	- Primary account pays for all member accounts
	- Bulk discounts
- Hierarchical groupings of accounts
	- Meet security, compliance & budgetary needs
- Service & API actions access control
### SCP
*Service Control Policies*
- Utilized by primary account
- Applied to individual member accounts / OU (org unit)
- Specify max. perms for member accounts in org
- Services // Resources // API actions
___

## Artifact
- Access compliance reports done by 3rd parties
___
## Shield
- Uses WAF
- Filters incoming traffic for signatures of bad actors
- Extensive ML capabilities
- Can recognize new threats as they evolve
### Standard
- Automatically protects all AWS customers
- No cost
- Protects from most common, frequently occurring types of DDoS attacks
- Uses variety of analysis techniques to detect malicious traffic
- Real time
### Advanced
- Paid service
- Provides detailed attack diagnostics
- Ability to detect & mitigate sophisticated DDoS attacks
- Integrates with CloudFront // Route 53 // ELB
	- WAF (write custom rules to mitigate complex DDoS attacks)
___
## KMS
*Key Management Service*
- Manage encryption keys
___
## Inspector
- Helps improve security & compliance of AWS deployed apps
- Runs auto security assessment against infrastructure
- Checks for deviations of best security practices
- Exposure of EC2 instances // Vulnerability
- Network config reachability piece
- Amazon agent (can be installed on EC2 instances)
- Security assessment service
___
## GuardDuty
- Threat detection
- Analyses continuous streams of metadata generated from account & network activity
- CloudTrail events // VPC Flow logs // DNS logs
- Uses integrated threat intelligence to identify threats more accurately
	- Known malicious IP addresses // Anomaly detection // ML
- Runs independently from other Services
	- Won't effect performance & availability
___