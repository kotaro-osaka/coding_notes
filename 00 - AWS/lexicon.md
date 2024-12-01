# Concepts
___
## Multitenancy
- Shared underlying Hardware between machines
___
## CaaS
*Compute as a service*
___
## Regions
- Located closest to high traffic demands
- Connected via high speed fiber network
- Isolated unless customer requests data export
	- Government compliance requirement can be maintained
	- Local laws
### Choosing Region
1. Compliance requirements
2. Proximity to customer
3. AWS feature availability
4. Pricing
___
## AZ
*Availability Zone*
- Data center group
- Data centers have redundant power, networking & connectivity
- Run across at least 2 AZ in a Region
___
## Messaging & Queuing
- Requests are placed in buffer and queued for processing
- Removes danger of requests being dropped when processing instance is out of synch
___
## Monolithic Apps & Microservices
- Apps made out of components
	- Components communicate with each other (transmit data // fulfill requests)
### Tightly coupled architecture
- Direct connections: Tight synchronization must be ensured to eliminate possibility of dropped messages
- Single failure can cause cascading failure
__
___
## Microservices
- App components are loosely coupled
- Independent components = Failure doesn't effect other components
### Loosely coupled architecture
- Indirect connections: Buffer stores messages until they can be processed 
- Single failure won't cause cascading failure
- Doesn't rely on other services
___
## Serverless
- Underlying infrastructure cannot be seen or accessed
___
## IGW
*Internet Gateway*
___
## VPG
*Virtual Private Gateway*
- Allows VPN connection between personal datacenter & VPC
___
## Network ACL
*Network Access Control List*
*Stateless*: Operates without tracking packet states, treating each packet independently
- Stores predefined permission for packet traffic
- Permissions based on sender & type of communication
___
## Security Group
*Stateful*: Maintains packet states by tracking inbound cached traffic
- Isolate instances in subnets
- Configured to accept specific requests
- Allows all packets to leave security group boundary
___
## WORM
*Write once/read many*
___
## RDBMS
*Relational Database Management System*
- Data stored in relation to other data
___
## Lift-and-shift migration
- Moving databases from on-premises infrastructure to cloud
- No significant mods (minimal code changes)
- Reduced hardware costs // Scalability // Easier management
- May require post-migration optimization
___
## Data Warehousing
- Centralized repository
- Collecting; Organizing; Storing large volumes of structured data from various sources
- Data is processed, transformed & optimized for querying & analysis
### Use Cases
- Consolidate data from disparate sources
- Perform complex analytics
- Generate reports
- Make data-driven decisions to improve operations, strategy & decision-making processes
___
## Block Chain
- Distributed ledger system
- Lets multiple parties run transactions & share data
- Decentralized
___
## ALB
> App Load Balancing
___
## NLB
> Network Load Balancing