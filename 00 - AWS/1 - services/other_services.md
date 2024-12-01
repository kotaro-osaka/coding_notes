# Other Services
___
## ELB
*Elastic Load Balancing*
> Regional construct: Not bound to instances
- Automatically scalable
- Handles additional throughput with no change to $/h
### Process
**Scale out**
1. Instances scale out & go online
2.  notifies ELB of new available instances
**Scale in**
1. ELB stops all new traffic
2. Waits for existing requests to complete (drain out)
3. Instance scaling service terminates instances

## SQS
*Simple Queue Service*
- Send // Store // Receive messages
- Exists between components
- Any volume
## SNS
*Simple Notification Service*
- Can sends messages to services & end users 
- **End users**: Mobile Push // SMS // Email
### Publish-Subscribe Model
1. Create **SNS topic** (Channel for messages to be delivered)
2. Configure subscribers to SNS topic
3. (publish messages in topic)
- **Subscribers**: SQS queues // Lambda function // HTTP/HTTPS Webhooks