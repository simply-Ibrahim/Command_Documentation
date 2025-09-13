# Nmap Port Scanning Task 
Targate :- scanme.nmap.org \
Do port Scanning On The given target to find the following:
1. 2 Open UDP Ports
2. 2 Open TCP Ports
3. Top 1000 Open TCP Ports
4. If Ports 10,31,80,9091 are open or not
5. Scan All TCP Open Ports


## 2 Open TCP PORTS
` namp <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 13:01 EDT
Stats: 0:00:28 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 94.33% done; ETC: 13:02 (0:00:01 remaining)
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.27s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
rDNS record for 45.33.32.156: 156.32.33.45.in-addr.arpa
Not shown: 994 closed tcp ports (reset)
PORT      STATE    SERVICE
22/tcp    open     ssh
25/tcp    filtered smtp
80/tcp    open     http
5060/tcp  filtered sip
9929/tcp  open     nping-echo
31337/tcp open     Elite
```


## 2 Open UDP PORTS
` namp -sU --top-ports <port> <targate> `


Example 
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 13:20 EDT
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.29s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
rDNS record for 45.33.32.156: 156.32.33.45.in-addr.arpa
Not shown: 97 closed udp ports (port-unreach)
PORT     STATE         SERVICE
68/udp   open|filtered dhcpc
123/udp  open          ntp
5060/udp open|filtered sip

Nmap done: 1 IP address (1 host up) scanned in 110.81 seconds
```
### OPEN PORTS ARE 68,123 & 5060

