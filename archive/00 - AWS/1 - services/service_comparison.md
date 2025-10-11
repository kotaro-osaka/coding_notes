# Service Comparison
___
## EBS | S3
|              | EBS                                  | S3                                     |
| ------------ | ------------------------------------ | -------------------------------------- |
| **Storage**  | ≤`16 TiB`                            | Unlimited storage<br>Objects ≤`5 TB`   |
|              | Survives termination of EC2 instance | Write once/read many                   |
|              | Solid state by default               | 99.999999999% durability               |
|              | HDD options                          |                                        |
| **Use case** | Complex read/write change functions  | Complete objects<br>Occasional changes |
|              |                                      | Web enabled                            |
|              |                                      | Regionally distributed                 |
|              |                                      | Offers cost savings                    |
|              |                                      | Serverless                             |
### Storage Methods
|            | Block         | Object                |
| ---------- | ------------- | --------------------- |
| **Saving** | Modifies file | Reuploads entire file |
## EBS | EFS
|                  | EBS                               | EFS                                                            |
| ---------------- | --------------------------------- | -------------------------------------------------------------- |
|                  | Volumes attach to EC2 instances   | Multiple instances reading/writing simultaneously              |
| **Provisioning** | Volumes don't automatically scale | Automatically scales                                           |
| **Location**     | AZ level resource                 | Regional resource<br>(Accessible by any regional EC2 instance) |
|                  |                                   | Linux file system                                              |
## RDS | DynamoDB
|              | RDS                                               | DynamoDB                        |
| ------------ | ------------------------------------------------- | ------------------------------- |
|              | Automatic high availability;<br>Recovery provided | Key-value                       |
|              | Customer ownership of data                        | Massive throughput capabilities |
|              | Customer ownership of schema                      | PB size potential               |
|              | Customer control of network                       | Granular API access             |
| **Use case** | Business analytics                                | Anything else                   |
