# Security Concepts
___
## Dos Attack
*Denial-of-service*
- Single source attack
- Overloads system with extensive network traffic
### Slow Loris Attack
- Target web servers
- Exploit HTTP/TCP connection behavior
- Attacker sends partial HTTP requests (keep connection open)
- Consume server res (sockets // memory)
- Effective against servers with limited concurrent connection handling capabilities
#### Prevention
- ELB (*Elastic Load Balancer*)
- Only sends complete requests
- ELB waits until request is complete
##### Reliability of Prevention
- ELB is salable at region level
- Entire AWS region would have to be overwhelmed
___
## DDoS Attack
*Distributed denial-of-service*
- Multiple source attack (Bots // Group of attackers)
### UDP Flood
*User Datagram Protocol*
- Floods target with UDP packets
- Overloads target's network
- Difficult to trace due to spoofed IP addresses
- Request specifies spoofed return IP address (victim's address)
#### Prevention
- Security Group
- Only allow proper request traffic
##### Reliability of Prevention
- Security Groups operate at AWS network level (not instance level)
- Entire AWS region would have to be overwhelmed
___
## Spoofed IP Addresses
- Falsified / altered IP addresses
- Conceal true origin of traffic
___
## HTTP Attacks
- Target web servers / apps
- Exploit vulnerabilities in HTTP protocol // Web server software
- HTTP flooding // HTTP request smuggling // HTTP parameter pollution
- Disrupt service // Steal data // Gain unauthorized access
- Mitigation: Rate limiting // web app firewalls // secure coding practices
___
## WAF
*Web App Firewall*
___
## Encryption at Rest
- Encryption of idle data (in storage)
## Encryption in Transit
- Encryption of data during transit
## SSL
*Secure Sockets Layer*
