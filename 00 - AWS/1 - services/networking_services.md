# Networking Services
___
## CloudFront
*Content Delivery Network*
- Run in edge locations to provide availability to customers
- Caches copy from host instance to edge location
## Route 53
- DNS service
- Buy domain names
### Routing Policies
- Latency-based routing
- Geolocation DNS: Customer's location
- Geoproximity routing
- Weighted round robin
## Outposts
- Fully operational 'Mini-Region' in customer's datacenter
- Installed, owned & operated by Amazon
- Uses AWS functionality
- Isolated in customer's location
## Elastic Beanstalk
- Provision EC2 based environments
- Builds environment from provided code & configs
## CloudFormation
> Infrastructure as code 
- Define AWS resources using JSON // YAML CloudFormation templates
- Storage // Database // Analytics // ML
- Manages back end calls to APIs
## VPC
*Virtual Private Cloud*
- Private network
- Allows private // public subnetting
- Used to define resource ranges
### Subnets
- Packets are checked against Network ACL when crossing subnet boundaries
- Hold Security Groups
#### Public subnet
- Has access to VPC's IGW
#### Private subnet
- Has access to VPC's VPG

## Direct Connect
- Physical connection
	- VPC - Direct Connect endpoint
	- **Direct Connect Location**: Direct Connect endpoint - Customer / Partner router
	- **Direct Connect Location - Corporate Data center**: Customer / Partner router - Content router/firewall
- Private dedicated fiber connection from corporate datacenter to AWS
- Established by local Direct Connect partner
- Meet high regulatory & compliance needs
- Avoid bandwidth issues