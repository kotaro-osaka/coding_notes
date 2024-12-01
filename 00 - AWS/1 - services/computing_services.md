# Computing Services
___
## EC2
*Elastic Compute Cloud*
- Virtual Server
- Shared hosting with VM & hypervisor
- Pay for running instances
### Instance Store Volumes
- Local temp storage (deleted on instance termination)
- Attached to underlying Host
### Use Cases
- Host traditional apps
- Full access to OS
### Configurations 
- OS: Windows; Linux
- Internal business apps; Web apps; Databases; Thrid-party software
- Resizable (vertical scaling)
- Networking: Request types; public/private accessibility
### Requirements
- Patch instances when new software packages are available
- Setup scaling of instances
- Ensure architecture enables high availability
### Instance types/families

|              | General purpose                                 | Compute opt.                                                | Memory opt.      | Accelerated computing                                                       | Storage opt.                       |
| ------------ | ----------------------------------------------- | ----------------------------------------------------------- | ---------------- | --------------------------------------------------------------------------- | ---------------------------------- |
| **Useage**   | Balanced resources                              | Compute intensive tasks                                     | Memory intensive | Hardware accelerators                                                       | High perf. for locally stored data |
| **Examples** | Diverse workloads:<br>Web servers // Code repos | Gaming servers // High perf. comp. (HPC) // Scientific mod. |                  | Floating point number calc. // Graphics processing // Data pattern matching |                                    |
### Pricing
|               | On-demand                  | Savings plan                               | Reserved instances                                              |
| ------------- | -------------------------- | ------------------------------------------ | --------------------------------------------------------------- |
| **Pricing**   | $/h // $/s                 | $/h<br>1yr // 3yr plan                     | All-upfront // Partial-upfront // No-upfront<br>1yr // 3yr plan |
| **Benefits**  | no long term commitment    | Savings up to 72% on compute usage         | Up to 75% discount                                              |
|               | no upfront payments        | Low pricing for consistent amount of usage |                                                                 |
| **Use case**  | Getting started // Testing |                                            | Steady state work loads // Predictable usage                    |

|               | Spot instances                                | Dedicated Hosts            |
| ------------- | --------------------------------------------- | -------------------------- |
| **Pricing**   |                                               | Expensive                  |
| **Benefits**  | Up to 90% of on-demand price                  | No shared tendency of host |
|               | Request spare EC2 capacity                    |                            |
| **Drawbacks** | Amazon can reclaim at any time (2min warning) | Most expensive             |
| **Use case**  |                                               | Meeting compliance req.    |
### Scaling
- Automatic addition/removal of instances in response to changing app demand
- Maintain app availability

| Dynamic scaling               | Predictive scaling                                                            |
| ----------------------------- | ----------------------------------------------------------------------------- |
| *Responds* to changing demand | Automatically *schedules* right number of instances based on predicted demand |
#### Auto scaling Config
![[auto_scaling_group.png|250]]
- Desired capacity default: Minimum
___
## Lambda
- Serverless computation
- **Lambda function**: Stores code
- Scales Lambda function to meet demand
- Runs code for <15min
	- Suited for quick processing
- Pay for compute time
### Use Cases
- Short running functions
- Service-oriented apps
- Event-driven apps
- No provisioning/managing servers
### Process
1. Upload code to Lambda function
2. Configure Trigger
3. Service waits for trigger
4. Code is run in managed environment when Trigger is detected
___
## ECS
#containerization
*Elastic Container Service*
- Run containerized apps at scale without managing container orchestration
- Primarily for Docker
- Provides control plane for managing container deployments
- Offers infrastructure and deployment strategy flexibility
- Containers run on EC2 instances
- Use API calls to launch/stop Docker-enabled apps
___
## EKS
#containerization
*Elastic Kubernetes Service*
- Supports Docker and others
- Provides scalability and ease of management for Kubernetes clusters
- Offers Kubernetes control plane management
- Containers run on EC2 instances
___
## Fargate
#containerization
- Serverless compute engine for ECS & EKS
- Infrastructure management
- Pay-as-you-go (/ms)
- Tasks run in customer VPC
- ALB & NLB support (ELB not supported)
### Security
- Customer owns & manages tasks
- No SSH access to infrastructure
- Cluster-level isolation
### Use Cases
- Long running services
- High variable workloads
- Monolithic app portability
- Batch jobs and micro services
