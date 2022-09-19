## Ping:
*Can be handful for DNS checks (up / or down) | is a DNS tool to resolves web addresses to an IP address.
*Test reachability - determine round-trip time, and uses ICMP protocol
 
 $ ping www.google.com 

## Netstat:
*Network statistics
*Get info on host system TCP / UDP connections and status of all open and listening ports and routing table.
*Who you talking to?
*Who trying talking to you?

 $ netstat -a # (show all active connections) (servers)
 $ netstat -n # (hosts)
 $ netstat -b # (Show binaries Windows)
 
## Traceroute
*Traceroute - how packets get from host to another endpoint. Traceroute is helpful to see what routers are being hit, both internal and external.
*Take advantage of ICMP Time to Live (TTL) Exceeded error message
        The time in TTL refers to hops, not seconds or minutes.
        TTL=1 is the first router.
        TTL=2 is the second router, and so on.
*As shown above, on HOP 2 the TTL exceeded and back to the device A, counting 3 on TTL for the next HOP.
 
 $ traceroute google.com

## arp
*Address resolution protocol - caches of ip-to-ethernet
*Determine a MAC address based on IP addresses
*option -a: view local ARP table
 
 $ arp -a
 
## ip addr
 
 $ ip addr

## nslookup
*Query Internet name servers interactively; check if the DNS server is working

 $ nslookup www.certifiedhacker.com

## tcpdump
*Tcpdump is a data-network packet analyzer computer program that runs under a command line interface. It allows the user to display TCP/IP and other
packets being transmitted or received over a network to which the computer is attached. Distributed under the BSD license, tcpdump is free software

 $ tcpdump -i eth0
 






