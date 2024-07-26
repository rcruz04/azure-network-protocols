<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. 

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- [Create our Resources](#step1)
- [Observe ICMP Traffic](#step2)
- [Observe SSH Traffic](#step3)
- [Observe DHCP Traffic](#step4)
- [Observe DNS Traffic](#step5)
- [Observe RDP Traffic](#step6)



<h2 id="step1">1. Create our Resources</h2>



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h3>
  
*Create a Resource Group* 
</h3>

<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Create a Windows 10 Virtual Machine*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Create a Linux Virtual Machine*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Observe Your Virtual Network within Network Watcher*
</h3>
<p>
substitution text
</p>
<br />



<h2 id="step2">2. Observe ICMP Traffic</h2>



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Use Remote Desktop to connect to your Windows 10 Virtual Machine*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Install Wireshark*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Open Wireshark and filter for ICMP traffic*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Ping Ubuntu VM from Windows VM*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Ping a Public Website*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Initiate a perpetual ping to the Ubuntu VM*
</h3>
<p>
substitution text
</p>
<br />



<h2 id="step3">3. Observe SSH Traffic</h2>



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Filter for SSH traffic*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*SSH into your Ubuntu VM*
</h3>
<p>
substitution text
</p>
<br />



<h2 id="step4">4. Observe DHCP Traffic</h2>



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Filter for DHCP traffic*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Issue your VM a new IP address from the command line*
</h3>
<p>
substitution text
</p>
<br />



<h2 id="step5">5. Observe DNS Traffic</h2>



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Filter for DNS traffic*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Use nslookup*
</h3>
<p>
substitution text
</p>
<br />



<h2 id="step6">6. Observe RDP Traffic</h2>



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Filter for RDP traffic*
</h3>
<p>
substitution text
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>

*Observe Traffic*
</h3>
<p>
substitution text
</p>
<br />














