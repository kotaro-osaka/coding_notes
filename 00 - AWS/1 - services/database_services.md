# Database Services
___
## RDS
*Relational Database Service*
- Amazon Aurora // PostgreSQL // MySQL // MariaDB // Oracle Database //Microsoft SQL Server
- Automated patching
- Backups
- Redundancy
- Failover
- Disaster recovery
### Aurora
- MySQL // PostgreSQL
- 1/10th cost of commercial databases
- Data replication across facilities (6 copies across 3 AZs)
- `≤15` read replicas
- Continuously backs up to S3
- Point-in-time recovery
- Reduce costs by reducing unnecessary input/output
- `≤5x` faster than standard MySQL
- `≤3x` faster than standard PostgreSQL
___
## DynamoDB
- Serverless database
- No-SQL
- Non-relational
- Key-value pairs
- Items with attributes in Tables
- Auto scaling
- Redundant storage across AZs
- 1ms response time
- Query key from 1 table
___
## Redshift
- Data warehousing
- Large scaling
- `≤10x` higher performance than traditional databases business intelligence workloads
___
## DMS
*Database Migration Service*
- Migration between source & target database
- Source database remains fully operational during migration
- Downtime is minimized for apps that rely on source database
- Source & target database don't have to be of same type
### Homogenous databases
*Databases of same types*
- Straight forward due to compatible schema structures, data types & database code
- Source: On-premises // EC2 // RDS
- Target: EC2 // RDS
#### Process
1. Create migration task
2. Connect to source & target databases
### Heterogenous databases
*Databases of different types*
#### Process
1. Convert schema structures & database code with Schema conversion tool
2. Migrate data via DMS
### Other Use Cases
- Development & test database migrations
	- Developers test against production data without affecting production users
	- DMS used to migrate copy of database to dev/test environment
	- Once / Continuously
- Database consolidation
	- Consolidate several databases into 1 central database
- Cotonous database replication
	- Perform continuous data replication
	- Disaster recovery // Geographic separation
___
## DocumentDB
- Document database service
- Supports MongoDB workloads
### Use Cases
- Content management
- Catalogues
- User profiles
___
## Neptune
- Graph database
### Use Cases
- Build & run apps that work with highly connected datasets
- Social networking
- Recommendation engines
- Fraud detection
- Knowledge graphs
___
## QLDB
*Quantum Ledger Database*
- Immutable Ledger
### Use Cases
- Review complete history of all changes made to app data
- Supply chain tracking with insurances that nothing is lost
- Banking/financial records that require 100% immutability
___
## Managed Blockchain
- Create & manage blockchain networks with open-source frameworks
___
## ElastiCache
#datanase_accelerator
- Add caching layers on top of database
- Help improve read times of common requests (ms -> μs)
- Removes heavy lifting of launching, uplift & maintenance
- Supports Redis & Memcached
___
## DAX
#database_accelerator
*DynamoDB Accelerator*
- Native caching layer (in-memory cache)
- Designed to improve read times for non-relational data (ms -> μs)