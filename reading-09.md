## HTTP Basics
- a stateless application layer protocol for communicating between hosts and clients (req/res)
  -usually uses TCP/IP  
  - default port 80
  - sent via URL
  
### Structure:
- http(s)/ = protocol
- www.domain.com/ = host
- :1234/ = port
- path/ = path to resource/local path
- res?a=b&x=y/ = query

### HTTP Verbs
- HEAD = like GET but without body
- TRACE = each proxy or gateway the request goes through
- OPTION = on client side, can modify request
- requests: url & verbs
- response: status codes & message body

## DNS
- domain name system (uses words instead of IP addresses because easier to remember)
1. Browser > 
     - search caches to see if know IP for a site; if not go to resolver
1. OS > 
    - search caches to see if know IP for a site; if not go to resolver
1. Resolver > 
    - checks next
    - server (usually ISP = Internet Service Provider)
1. Root Servers > 
    - checksd next
    - 13 around the world
    - at the top of DNS hierarchy
1. Top Level Domain Servers > 
    - checks next
    - .com, .org, .net
1. Authoritative Name Servers
    - checks nect
    - told about purchased domains by domain registrar
    - can run a WHOIS query to find out who is the ANS of your domain
