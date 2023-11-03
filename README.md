<h1>Performing a Denial of Service Attack from the Wan Lab</h1>

<h2>Description</h2>
The laboratory environment comprises an internal network, which includes a Windows server (IP address: 192.168.1.10), a Metasploitable server (IP address: 192.168.1.30), and a Linux sniffer machine without a designated IP address. At the network perimeter, there is a pfSense firewall with an IP address of 203.0.113.100. Additionally, an external Windows 8.1 Attack machine with an external IP address of 175.45.176.200 is present.

In this experiment, we will utilize a software tool known as "Low Orbit Ion Cannon" (LOIC) to execute TCP, UDP, and HTTP flood attacks on the network. The Linux machine will serve as a packet capture device, allowing us to record the packets generated during each type of flood.

It is important to emphasize that LOIC is not a legitimate or legal tool; instead, it is a piece of software commonly associated with malicious activities, specifically Distributed Denial of Service (DDoS) attacks. These attacks involve inundating a target computer system or network with an excessive volume of traffic, thereby rendering it inaccessible to legitimate users. LOIC is just one of the tools that can be exploited to carry out such attacks.
<br />

<h2>Project walk-through:</h2>

<p align="center">
Lab Topology: <br/>
<img src="https://imgur.com/9qQbUOC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Start by accessing the Linux Sniffer machine  <br/>
<img src="https://imgur.com/3JqTn6y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Open the Linux terminal and determine the IP Address for the Sniffer Machine: <br/>
<img src="https://imgur.com/ogm0CQV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use the following command to remove the IP address of the Linux Sniffer machine:  <br/>
<img src="https://imgur.com/CIKFPJm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use the following command to create a text file for the packets sniffed during the DDOS Attacks:  <br/>
<img src="https://imgur.com/UzCMdoM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
