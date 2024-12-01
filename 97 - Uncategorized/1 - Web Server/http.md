# HTTP
___
## Setup
- `nc -k -l 8080` (listen for incoming connection on port 8080 with *netcat*)
- `curl localhost:8080` (HTTP request with *curl*)
## Structure
```http
GET / HTTP/1.1
Host: localhost:8080
User-Agent: curl/
```
