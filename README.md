<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setting up our resources in Azure.
- Ensuring connectivity between the Client and Domain Controller.
- Installing Active Directory.
- Creating an Admin and Normal User Account within AD.
- Joining a Client to our Domain.
- Setting up Remote Desktop for non-administrative users on the Client
- Creating 10,000 users and logging in with one of them.

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, create two VMs in Azure. One should be using Windows 10 and the other should be using Windows Server. Make sure they're both in the same RG and using the same Vnet. Check the network topology in Network Watcher to make sure everything looks right (refer to the picture above). After all of that, we're going to change our Domain Controller's (Server 2022) private IP address to static. In Azure, navigate to Virtual Machines -> DC-1 -> Networking -> Network Interface -> IP Configurations -> Private IP Address -> Change to Static.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, we're going to establish and verify a connection between Client-1 and DC-1. Log into Client-1 and ping DC-1's private IP -t (perpetual ping). Now, log into DC-1 and enable ICMPv4 on the local Windows Firewall. Check back with Client-1 to verify that the ping is now getting a response.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we'll install Active Directory on DC-1. Go into the Server Manager and click "Add Roles and Features". Click through the first few prompts, and then select Active Directory Domain Services. Click through the rest of the prompts and then click Install. Once AD is done installing, click on the flag icon in the top right, then click on "Promote this server to a domain controller". Select the option to create a new forest. Use mydomain.com. Click through the prompts and click Install at the end. Sign back into DC-1 as mydomain.com\labuser (or mydomain.com\whatever your username is).
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
Continued <a href="https://github.com/TrevorBrandtIT/dns-intuition">here.</a> Thank you for following along!
</p>
<br />
