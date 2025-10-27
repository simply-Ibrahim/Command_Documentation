**Target** -  Vampire Breakout

**Author** - Ibrahim H Siamwala

## Lab Setup

- **Host** - Kali linux (Attacker)
- **Target** - VirtualBox VM imported from breakout 02 (Target)
- **Network** - Host Only / NAT with host-only adapter

- `nmap -A 192.168.1.12`

```
──(kali㉿kali)-[~]
└─$ nmap -A 192.168.1.12                          
Starting Nmap 7.95 ( https://nmap.org ) at 2025-10-27 01:31 EDT
Nmap scan report for 192.168.1.12 (192.168.1.12)
Host is up (0.0015s latency).
Not shown: 995 closed tcp ports (reset)
PORT      STATE SERVICE     VERSION
80/tcp    open  http        Apache httpd 2.4.51 ((Debian))
|_http-title: Apache2 Debian Default Page: It works
|_http-server-header: Apache/2.4.51 (Debian)
139/tcp   open  netbios-ssn Samba smbd 4
445/tcp   open  netbios-ssn Samba smbd 4
10000/tcp open  http        MiniServ 1.981 (Webmin httpd)
|_http-title: 200 &mdash; Document follows
|_http-server-header: MiniServ/1.981
20000/tcp open  http        MiniServ 1.830 (Webmin httpd)
|_http-server-header: MiniServ/1.830
|_http-title: 200 &mdash; Document follows
MAC Address: 08:00:27:55:96:48 (PCS Systemtechnik/Oracle VirtualBox virtual NIC)
Device type: general purpose|router
Running: Linux 4.X|5.X, MikroTik RouterOS 7.X
OS CPE: cpe:/o:linux:linux_kernel:4 cpe:/o:linux:linux_kernel:5 cpe:/o:mikrotik:routeros:7 cpe:/o:linux:linux_kernel:5.6.3
OS details: Linux 4.15 - 5.19, OpenWrt 21.02 (Linux 5.4), MikroTik RouterOS 7.2 - 7.5 (Linux 5.6.3)
Network Distance: 1 hop

Host script results:
|_nbstat: NetBIOS name: BREAKOUT, NetBIOS user: <unknown>, NetBIOS MAC: <unknown> (unknown)
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2025-10-27T05:31:36
|_  start_date: N/A
|_clock-skew: 3s

TRACEROUTE
HOP RTT     ADDRESS
1   1.49 ms 192.168.1.12 (192.168.1.12)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 52.96 seconds
                                                               
```

- **Port 80 Apache httpd 2.4.51 ((Debian))**
**Screenshot :** 
![[Pasted image 20251027015956.png]]

- **By Inspecting This Page We got a Brainfuck text** 
**Screenshot :** 
![[Pasted image 20251027020209.png]]

- **Then we found The password of a user by decryption of the text**
```
++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>++++++++++++++++.++++.>>+++++++++++++++++.----.<++++++++++.-----------.>-----------.++++.<<+.>-.--------.++++++++++++++++++++.<------------.>>---------.<<++++++.++++++.
```
**Screenshot :** 
![[Pasted image 20251027020602.png]]

- **Now we will find the user for the password we got**
- **Tool :** enum4linux
- `sudo enum4linux -a 192.168.1.12`
- Got a user named **cyber**

```
┌──(kali㉿kali)-[~]
└─$ sudo enum4linux -a 192.168.1.12 
[sudo] password for kali: 
Starting enum4linux v0.9.1 ( http://labs.portcullis.co.uk/application/enum4linux/ ) on Mon Oct 27 02:12:27 2025

 =========================================( Target Information )=========================================

Target ........... 192.168.1.12                                                                                                                                                                                                            
RID Range ........ 500-550,1000-1050
Username ......... ''
Password ......... ''
Known Usernames .. administrator, guest, krbtgt, domain admins, root, bin, none


 ============================( Enumerating Workgroup/Domain on 192.168.1.12 )============================
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+] Got domain/workgroup name: WORKGROUP                                                                                                                                                                                                   
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
 ================================( Nbtstat Information for 192.168.1.12 )================================
                                                                                                                                                                                                                                           
Looking up status of 192.168.1.12                                                                                                                                                                                                          
        BREAKOUT        <00> -         B <ACTIVE>  Workstation Service
        BREAKOUT        <03> -         B <ACTIVE>  Messenger Service
        BREAKOUT        <20> -         B <ACTIVE>  File Server Service
        ..__MSBROWSE__. <01> - <GROUP> B <ACTIVE>  Master Browser
        WORKGROUP       <00> - <GROUP> B <ACTIVE>  Domain/Workgroup Name
        WORKGROUP       <1d> -         B <ACTIVE>  Master Browser
        WORKGROUP       <1e> - <GROUP> B <ACTIVE>  Browser Service Elections

        MAC Address = 00-00-00-00-00-00

 ===================================( Session Check on 192.168.1.12 )===================================
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+] Server 192.168.1.12 allows sessions using username '', password ''                                                                                                                                                                     
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
 ================================( Getting domain SID for 192.168.1.12 )================================
                                                                                                                                                                                                                                           
Domain Name: WORKGROUP                                                                                                                                                                                                                     
Domain Sid: (NULL SID)

[+] Can't determine if host is part of domain or part of a workgroup                                                                                                                                                                       
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
 ===================================( OS information on 192.168.1.12 )===================================
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[E] Can't get OS info with smbclient                                                                                                                                                                                                       
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+] Got OS info for 192.168.1.12 from srvinfo:                                                                                                                                                                                             
        BREAKOUT       Wk Sv PrQ Unx NT SNT Samba 4.13.5-Debian                                                                                                                                                                            
        platform_id     :       500
        os version      :       6.1
        server type     :       0x809a03


 =======================================( Users on 192.168.1.12 )=======================================
                                                                                                                                                                                                                                           
Use of uninitialized value $users in print at ./enum4linux.pl line 972.                                                                                                                                                                    
Use of uninitialized value $users in pattern match (m//) at ./enum4linux.pl line 975.

Use of uninitialized value $users in print at ./enum4linux.pl line 986.
Use of uninitialized value $users in pattern match (m//) at ./enum4linux.pl line 988.

 =================================( Share Enumeration on 192.168.1.12 )=================================
                                                                                                                                                                                                                                           
smbXcli_negprot_smb1_done: No compatible protocol selected by server.                                                                                                                                                                      

        Sharename       Type      Comment
        ---------       ----      -------
        print$          Disk      Printer Drivers
        IPC$            IPC       IPC Service (Samba 4.13.5-Debian)
Reconnecting with SMB1 for workgroup listing.
Protocol negotiation to server 192.168.1.12 (for a protocol between LANMAN1 and NT1) failed: NT_STATUS_INVALID_NETWORK_RESPONSE
Unable to connect with SMB1 -- no workgroup available

[+] Attempting to map shares on 192.168.1.12                                                                                                                                                                                               
                                                                                                                                                                                                                                           
//192.168.1.12/print$   Mapping: DENIED Listing: N/A Writing: N/A                                                                                                                                                                          

[E] Can't understand response:                                                                                                                                                                                                             
                                                                                                                                                                                                                                           
NT_STATUS_OBJECT_NAME_NOT_FOUND listing \*                                                                                                                                                                                                 
//192.168.1.12/IPC$     Mapping: N/A Listing: N/A Writing: N/A

 ============================( Password Policy Information for 192.168.1.12 )============================
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           

[+] Attaching to 192.168.1.12 using a NULL share

[+] Trying protocol 139/SMB...

[+] Found domain(s):

        [+] BREAKOUT
        [+] Builtin

[+] Password Info for Domain: BREAKOUT

        [+] Minimum password length: 5
        [+] Password history length: None
        [+] Maximum password age: 37 days 6 hours 21 minutes 
        [+] Password Complexity Flags: 000000

                [+] Domain Refuse Password Change: 0
                [+] Domain Password Store Cleartext: 0
                [+] Domain Password Lockout Admins: 0
                [+] Domain Password No Clear Change: 0
                [+] Domain Password No Anon Change: 0
                [+] Domain Password Complex: 0

        [+] Minimum password age: None
        [+] Reset Account Lockout Counter: 30 minutes 
        [+] Locked Account Duration: 30 minutes 
        [+] Account Lockout Threshold: None
        [+] Forced Log off Time: 37 days 6 hours 21 minutes 



[+] Retieved partial password policy with rpcclient:                                                                                                                                                                                       
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
Password Complexity: Disabled                                                                                                                                                                                                              
Minimum Password Length: 5


 =======================================( Groups on 192.168.1.12 )=======================================
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+] Getting builtin groups:                                                                                                                                                                                                                
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+]  Getting builtin group memberships:                                                                                                                                                                                                    
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+]  Getting local groups:                                                                                                                                                                                                                 
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+]  Getting local group memberships:                                                                                                                                                                                                      
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+]  Getting domain groups:                                                                                                                                                                                                                
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[+]  Getting domain group memberships:                                                                                                                                                                                                     
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
 ==================( Users on 192.168.1.12 via RID cycling (RIDS: 500-550,1000-1050) )==================
                                                                                                                                                                                                                                           
                                                                                                                                                                                                                                           
[I] Found new SID:                                                                                                                                                                                                                         
S-1-22-1                                                                                                                                                                                                                                   

[I] Found new SID:                                                                                                                                                                                                                         
S-1-5-32                                                                                                                                                                                                                                   

[I] Found new SID:                                                                                                                                                                                                                         
S-1-5-32                                                                                                                                                                                                                                   

[I] Found new SID:                                                                                                                                                                                                                         
S-1-5-32                                                                                                                                                                                                                                   

[I] Found new SID:                                                                                                                                                                                                                         
S-1-5-32                                                                                                                                                                                                                                   

[+] Enumerating users using SID S-1-22-1 and logon username '', password ''                                                                                                                                                                
                                                                                                                                                                                                                                           
S-1-22-1-1000 Unix User\cyber (Local User)                                                                                                                                                                                                 

[+] Enumerating users using SID S-1-5-32 and logon username '', password ''                                                                                                                                                                
                                                                                                                                                                                                                                           
S-1-5-32-544 BUILTIN\Administrators (Local Group)                                                                                                                                                                                          
S-1-5-32-545 BUILTIN\Users (Local Group)
S-1-5-32-546 BUILTIN\Guests (Local Group)
S-1-5-32-547 BUILTIN\Power Users (Local Group)
S-1-5-32-548 BUILTIN\Account Operators (Local Group)
S-1-5-32-549 BUILTIN\Server Operators (Local Group)
S-1-5-32-550 BUILTIN\Print Operators (Local Group)

[+] Enumerating users using SID S-1-5-21-1683874020-4104641535-3793993001 and logon username '', password ''                                                                                                                               
                                                                                                                                                                                                                                           
S-1-5-21-1683874020-4104641535-3793993001-501 BREAKOUT\nobody (Local User)                                                                                                                                                                 
S-1-5-21-1683874020-4104641535-3793993001-513 BREAKOUT\None (Domain Group)

 ===============================( Getting printer info for 192.168.1.12 )===============================
                                                                                                                                                                                                                                           
No printers returned.                                                                                                                                                                                                                      


enum4linux complete on Mon Oct 27 02:13:07 2025

```

- **Now we will open the webpages on port 10000 & 20000**
**Screenshot :** 
![[Pasted image 20251027022743.png]]
- **Not on port 10000**
**Screenshot :**
![[Pasted image 20251027023154.png]]
- **Got access to the webpage on port 20000**
