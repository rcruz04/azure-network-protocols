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
<img width="1470" alt="Screenshot 2024-07-25 at 10 04 26 PM" src="https://github.com/user-attachments/assets/2bbb34d6-aa59-4072-a4e2-5233c7fcab0b">
</p>
<h3>

*Create a Resource Group* 
</h3>
<p>
  
If you haven't already, set up your azure account to get some free credits. Then go to [portal.azure.com/](https://portal.azure.com/) and go to the search bar and search "resource group" and click on the cube with the brackets. Click create and name the reasource group "network_lab" and finish making the reasource group.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-25 at 10 13 23 PM" src="https://github.com/user-attachments/assets/31ff57d1-a47e-43e3-a25c-fc4bb5ffefe1">
</p>
<h3>

*Create a Windows 10 Virtual Machine*
</h3>
<p>
Go to the same search bar and search "virtual machine" and click on the computer. After name the VM "VM1" with the username "labuser" and a password you can remember. After youre finished it should look something like the picture and click create to start the deplyment process.
</p>
<br />

<p>
<img width="1470" alt="Screenshot 2024-07-25 at 10 21 52 PM" src="https://github.com/user-attachments/assets/1ba8a8e9-49a1-4376-b603-57b30dc9b662">
</p>
<h3>

*Create a Linux Virtual Machine*
</h3>
<p>
In the same way create a linux virtual machine and call it "VM2" with the same username and password (this is not best practice but for the lab its fine). <ins>Make sure to select the same VNET under the network tab</ins> it wont work if you don't.
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














