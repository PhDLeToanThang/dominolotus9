# Domino Lotus 9:
 IBM Domino Lotus v9 for DevOps vs vSphere
 Readme Text Guide - Demo Pilot Setup Domino Server v9  and Guide Setup Lotus Administrator + Lotus Design + Lotus Notes  for Administration, Developers, User Client.
###  0. Download Software vs Ebook reference: 
     https://1drv.ms/u/s!AtT2yQnThe-ykLYVDa-N4hFPjELxVw?e=yWQIyJ
---
###  1. How to Setup Domino Server v9 reference Blog share guide link: 
     https://thangletoan.wordpress.com/2016/04/11/ibm-domino-lotus-v-lotus-notes-client-chay-trn-nen-private-cloud-nhu-the-no/### comment-5142
###  2. Video/Audio interactive Simulator: 
     https://atcom.vn/hol-isim/dominolotus9/
---
###  3. OVA package for Deploy Sample QuickDemo or Pilot: 
- 	  on ESXi 6.5 or later or 
- 	  on VMware Player or 
- 	  on Workstation Pro 15 or later  
--- 
###  4. VM OS: Windows Server 2012 R2 Datacenter License
-  		User Admin OS: Administrator
-  		Password: VMware1!
-    IPv4 LAN: 192.168.100.85
---
###  Hosts fake Alias if you dont have DNS server / DNS Internal:
-    C:\windows\system32\drivers\etc\hosts
-    127.0.0.1  dominolotus.cloud.edu.vn
--- 
###  5. Firewall Windows Server Open Inboud Rule: TCP IP Port 2050,80,443,1352, 25, 110...
---
###  FAQ: Domino 9.0 / Domino 9.0.1 Install on Windows 2012 Service Won't Start Domino Server Issues Troubleshooting, Server Console ?
### Issue:
  After installing the 64-bit Domino server on Windows 64-bit 2012, you run into a problem starting IBM Domino. You can 
  start Domino from the command line, as an application, but starting as a Service doesn't work. You get a message that Domino started and stopped.

###  Solution:
   Perform both of the following:
   A: Update local hosts file
   If the Domino server's internal name is not part of DNS or it is behind a firewall so that the DNS resolved isn't the 
   right IP, then Domino won't start.
-  1. Edit the hosts file, at c:\windows\system32\drivers\etc\hosts.
-  2. Add the IP of the server, with the FQDN on the server doc, also add the HTTP alias(es), as well, as needed.
  e.g. 192.168.100.85 dominolotus.cloud.edu.vn
-  3. Save the file.
   B. Verify the ServerController = 1 setting is set in the notes.ini.
-  1. Edit the notes.ini file (e.g. d:\lotus\domino\notes.ini).
-  2. Do a find to locate the entry.
-  3. Change from 0 to 1, if the value is not already a 1.
   C: Add the TCPIP_ControllerTcpIpAddress entry to the notes.ini specifying the Controller address.
-  1. Edit the notes.ini file (e.g. d:\lotus\domino\notes.ini).
-  2. Do a find to locate the entry.
-  a. If the entry exists, update it or clear the value to the right of the equal (=) sign.
  TCPIP_ControllerTcpIpAddress=192.168.100.85, or just TCPIP_ControllerTcpIpAddress=
-  b. If the entry doesn't exist, add it like below: TCPIP_ControllerTcpIpAddress=
-  3. Save the file.
   D. Verify the Windows Firewall has port 2050 open.
   
###  Note: 
    It's a good time to also verify that ports 1352, 80, and 443 are open, since you probably are doing both Notes and ###  web apps.
    Control Panel --> Security (This option varies) --> Windows Firewall --> Advanced Settings --> Incoming Ports.
---
###  6. Domino Lotus 9 installed
-  Domino domain name: archibuslab
-  Country code: VN
-  Organization name: archibuslab
-  Organizational Unit name: it
-  Server Name: iscsi70/it/archibuslab/VN
-  User Admin Name Domino: Thang Toan Le/it/archibuslab/VN
-  Password Admin Domino: VMware1!
   Folder store full ID file for Server, Cert, Admin, Organization ID: 
   + C:\Program Files\IBM\Domino\data vs 
   + c:\Setup\LotusDomino9\Sample_ID_DominoServer9
