# Nmap on Metaspolitable
targate iP :- 192.168.0.111 \
Purpose :- Learning Nmap scan \
Author :- Ibrahim H Siamwala <simplyibrahim18@gmail.com>


## Top 1000 port Scanning
1. nmap Scan (ports) 
` nmap <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 02:13 EDT
Nmap scan report for 192.168.0.111
Host is up (0.017s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE SERVICE
21/tcp   open  ftp
22/tcp   open  ssh
23/tcp   open  telnet
25/tcp   open  smtp
53/tcp   open  domain
80/tcp   open  http
111/tcp  open  rpcbind
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
512/tcp  open  exec
513/tcp  open  login
514/tcp  open  shell
1099/tcp open  rmiregistry
1524/tcp open  ingreslock
2049/tcp open  nfs
2121/tcp open  ccproxy-ftp
3306/tcp open  mysql
5432/tcp open  postgresql
5900/tcp open  vnc
6000/tcp open  X11
6667/tcp open  irc
8009/tcp open  ajp13
8180/tcp open  unknown
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 1.34 seconds
```

## Scanning Specifc Port
2. Specific Scan 
` nmap -p <port> <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 02:18 EDT
Nmap scan report for 192.168.0.111
Host is up (0.0015s latency).

PORT   STATE SERVICE
21/tcp open  ftp
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 0.72 seconds
```


## Scanning specific Multipal Ports
3. Specific Multipal
` nmap -p <port 1,port 2> <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 02:22 EDT
Nmap scan report for 192.168.0.111
Host is up (0.015s latency).

PORT   STATE SERVICE
21/tcp open  ftp
80/tcp open  http
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 1.22 seconds
```


Example 2
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 02:26 EDT
Nmap scan report for 192.168.0.111
Host is up (0.0035s latency).

PORT   STATE  SERVICE
21/tcp open   ftp
81/tcp closed hosts2-ns
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 0.93 seconds
```


## Scanning First 100 ports 
4. Ports 1 - 100
` nmap -p <port 1> - <port 100> <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 02:29 EDT
Nmap scan report for 192.168.0.111
Host is up (0.016s latency).
Not shown: 94 closed tcp ports (reset)
PORT   STATE SERVICE
21/tcp open  ftp
22/tcp open  ssh
23/tcp open  telnet
25/tcp open  smtp
53/tcp open  domain
80/tcp open  http
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 0.47 seconds
```


## Scanning All Ports 
5. All ports
` nmap -p- <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 02:34 EDT
Nmap scan report for 192.168.0.111
Host is up (0.058s latency).
Not shown: 65505 closed tcp ports (reset)
PORT      STATE SERVICE
21/tcp    open  ftp
22/tcp    open  ssh
23/tcp    open  telnet
25/tcp    open  smtp
53/tcp    open  domain
80/tcp    open  http
111/tcp   open  rpcbind
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
512/tcp   open  exec
513/tcp   open  login
514/tcp   open  shell
1099/tcp  open  rmiregistry
1524/tcp  open  ingreslock
2049/tcp  open  nfs
2121/tcp  open  ccproxy-ftp
3306/tcp  open  mysql
3632/tcp  open  distccd
5432/tcp  open  postgresql
5900/tcp  open  vnc
6000/tcp  open  X11
6667/tcp  open  irc
6697/tcp  open  ircs-u
8009/tcp  open  ajp13
8180/tcp  open  unknown
8787/tcp  open  msgsrvr
50938/tcp open  unknown
52445/tcp open  unknown
53277/tcp open  unknown
60693/tcp open  unknown
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 55.26 seconds
```


## Scanning UDP Ports
6. udp Ports
` nmap -sU -p <port> <targate> `


Example
```
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-13 02:40 EDT
Nmap scan report for 192.168.0.111
Host is up (0.0052s latency).

PORT   STATE SERVICE
53/udp open  domain
MAC Address: 08:00:27:09:0E:2C (PCS Systemtechnik/Oracle VirtualBox virtual NIC)

Nmap done: 1 IP address (1 host up) scanned in 1.29 seconds
```
 
