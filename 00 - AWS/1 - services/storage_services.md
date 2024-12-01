# Storage Services
___
## EBS
*Elastic Block Store*
- Non-ephemeral storage
- EBS Volumes: Virtual hard drives (Block storage)
- Attachable to EC2 instances
- Variable Size; Type; Configs
- Writable in incremental backups (Snapshots)
- Only data that has changed since most recent snapshot is backed up
## S3
*Simple Storage*
- Store objects in buckets via API
- Store & retrieve unlimited amount of data
- Max. object size: `5TB`
- Object versioning
- Create multiple buckets
- Permission config
- Tiers for specification of access frequency
	- S3 Lifecycle management: Move data automatically between tiers
	- (E.g.: Standard > Standard-IA > Glacier)
- Static web hosting
### Classes
| **Classes**  | S3 Standard                              | S3 Standard-IA                                                          |
| ------------ | ---------------------------------------- | ----------------------------------------------------------------------- |
|              | 99.999999999% durability<br>after 1 year | *S3 Standard-Infrequent Access*                                         |
|              | Copies stored in 3 physical locations    | Used for data accessed less frequently with rapid retrieval when needed |
| **Use case** | Frequent accessed data                   | Backups; Desaster rec. files; (long term storage)                       |

| **Additional Classes** | S3 One Zone-IA                                       | S3 Intelligent-Tiering                                    |
| ---------------------- | ---------------------------------------------------- | --------------------------------------------------------- |
| **Info**               | Stores data in a single Availability Zone            | Small monthly monitoring & automation fee/object          |
|                        | Has a lower storage price than Amazon S3 Standard-IA | >30d: Standard-IA<br>If accessed in IA: Moved to Standard |
| **Use Case**           | Save costs on storage                                | Unknown/changing access patterns                          |
|                        | Easy reproduction of data in event of AZ failure     |                                                           |

| **""** | S3 Glacier Instant Retrieval                 | S3 Glacier Deep Archive     |
| ------ | -------------------------------------------- | --------------------------- |
| **""** | Retrieve objects within few milliseconds     | Retrieve objects within 12h |
| **""** | Archived data that requires immediate access | Lowest-cost                 |
|        |                                              | Archiving (access 1-2/yr)   |

| **""** | S3 Outposts                                                                                                                 |
| ------ | --------------------------------------------------------------------------------------------------------------------------- |
| **""** | S3 buckets on S3 Outposts                                                                                                   |
| **""** | Easier retrieval; storage; access of data on Outposts                                                                       |
|        | Durable & redundant storage across multiple devices & storage on Outpost                                                    |
|        | Local data residency requirements that must meet demanding performance needs<br>(by keeping data close to on-premises apps) |

#### S3 Glacier Flexible Retrieval
- Used for long term storage with non-rapid retrieval purposes
- Archives within Vaults
- Lock policy creation
	- WORM configurable
- Retrieval options (min-h)

## EFS
*Elastic File Storage*
- Managed file system
- Manages scaling & replication
- Accessible by multiple instances at same time