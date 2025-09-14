# Nmap Port Scanning Task 
Targate :- scanme.nmap.org \
Do port Scanning On The given target to find the following:
1. 2 Open UDP Ports
2. 2 Open TCP Ports
3. Top 1000 Open TCP Ports
4. If Ports 10,31,80,9091 are open or not
5. Scan All TCP Open Ports


## 2 Open TCP PORTS
` nmap -sS --top-ports <ports> <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 13:33 EDT
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.28s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
Not shown: 196 closed tcp ports (reset)
PORT     STATE    SERVICE
22/tcp   open     ssh
25/tcp   filtered smtp
80/tcp   open     http
5060/tcp filtered sip

Nmap done: 1 IP address (1 host up) scanned in 5.63 seconds
```
### OPEN PORTS ARE 22,25,80 & 5060


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


## Top 1000 Open TCP Ports
` nmap -sS <targate> `


Example 
```
tarting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 13:37 EDT
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.29s latency).
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

Nmap done: 1 IP address (1 host up) scanned in 34.23 seconds
```


## If Ports 10,31,80,9091 are open or not
` nmap -p <port 1 , port 2> <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 13:51 EDT
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.27s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
rDNS record for 45.33.32.156: 156.32.33.45.in-addr.arpa

PORT     STATE  SERVICE
10/tcp   closed unknown
31/tcp   closed msg-auth
80/tcp   open   http
9091/tcp closed xmltec-xmlmail

Nmap done: 1 IP address (1 host up) scanned in 1.47 seconds
```


## Scan All TCP Open Ports
` nmap -sS -p- <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-14 10:55 EDT
Nmap scan report for scanme.nmap.org (45.33.32.156)
Host is up (0.37s latency).
Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f
rDNS record for 45.33.32.156: 156.32.33.45.in-addr.arpa
Not shown: 65518 closed tcp ports (reset)
PORT      STATE    SERVICE
22/tcp    open     ssh
25/tcp    filtered smtp
80/tcp    open     http
1305/tcp  filtered pe-mike
1675/tcp  filtered pdp
5060/tcp  filtered sip
8718/tcp  filtered unknown
9929/tcp  open     nping-echo
11638/tcp filtered unknown
15028/tcp filtered unknown
17047/tcp filtered unknown
27681/tcp filtered unknown
31337/tcp open     Elite
34015/tcp filtered unknown
35861/tcp filtered unknown
37754/tcp filtered unknown
48294/tcp filtered unknown

Nmap done: 1 IP address (1 host up) scanned in 2136.58 seconds
```




