---
layout: post
title:  "Architecture and Modes of Cisco 1841 Router"
categories: Networking
---
Understand the external components of Cisco 1841 Router and learn three different modes User EXEC, Previleged and Global Configuration modes.

<h3>The front view of the router</h3>
![Frontview of Cisco 1841 Router](/assets/post-images/2020/cisco-1841-router-front-view.png)
The above is the front view of the Cisco router. We have the logo in the left side and Router model number on the right side which is Cisco 1841. Next, we have two system LED 1 and 2 as follows:
1. <i>System Power (SYS PWR) LED</i> - No power means off and blinking green means that the router is booting.
1. <i>System Activity (SYS ACT) LED</i> - Off means there is no traffic is flowing through the router and blinking green indicated that router is currently moving traffic from one of the port.

<h3>The back side of the router</h3>
![Back side of Cisco 1841 Router](/assets/post-images/2020/cisco-1841-back-view.png)
Let us see the different components and their meaning.

1. <i>Slot 1 (WIC, VWIC—data only, or HWIC)</i> - Network Card expansion slot
2. <i>Kensington Security Slot</i> - Secure the router physically from being stolen using the lock.
3. <i>Fast Ethernet ports and LEDs</i> - They have capacity to transmit data at the rate of 100 Mbps. There are three LEDs,  FDX (When it is on, it indicated full duplex and when off indicates half duplex operation), 100 (When it is on, it shows 100Mbps and when off indicates 10Mbps) and Link(When it is on, it means that the router is being connected to LAN).
4. <i>Console port</i> - (Management Port) Connecting directly with the computer using console cable for the purpose of configuring the router.
5. <i>Slot 0 (WIC, VWIC—data only, or HWIC)</i> - Network Card expansion slot
6. <i>CompactFlash memory card slot</i> - For inserting the flash memory card. There is light called (CF), which blinks if card is being inserted and being used. On the right of it there is (AM) LED, It is on on if advanced integration module is being installed in the router.
7. <i>USB port</i> - For plugging in an USB drive.
8. <i>Fast Ethernet ports and LEDs</i>
9. <i>Aux port</i> - (Management Port, Backup async port) It works as a backup console port. It can be used for dail-up port for remote router management.
10. <i>On/Off switch</i> - Power on and off the router.
11. <i>Input power connection</i> - Provide the AC power to the Router.

In addition to these, as shown in the image above, there is a ground port between on/off swich and Input power connection which allows the router to be grounded.

<h4>Methods of accessing the Router</h4>
1. <i>In-band access</i>: Used when the router is accessible through network when ip address is configured.
1. <i>Out-of-band access</i>: Physical access via console port.  

<h4>Modes of accessing the Router</h4>
<table>
<tr><th>Mode</th><th>Prompt</th><th>Description</th></tr>
<tr>
<td>User EXEC mode</td>
<td>Router></td>
<td>
1. First Level of Access<br />
2. Only supports basic commands.
</td>
</tr>
<tr>
<td>Privileged EXEC Mode</td>
<td>Router#</td>
<td>
1. Includes all the commands from User EXEC mode as well
2. Commands such as view configuration, debug, restart the router, etc.
</td>
</tr>
<tr>
<td>Global Configuration Mode</td>
<td>Router(config)#</td>
<td>
1. Modify the running router configuration
2. In this mode all the changes are made
</td>
</tr>
<tr><td></td><td>Router(config-if)#</td><td>Interface level within the configuration mode [Ethernet, Serial] (IP address, IPX address)</td></tr>
<tr><td></td><td>Router(config-router)#</td><td>Routing Engine Level [Rip, ospf] (network, version)</td></tr>
<tr><td></td><td>Router(config-line)#</td><td>Line level [vty, console] (password, login)</td></tr>
</table>

<h3>Commands for navigating to different modes</h3>
<table>
<tr><th>Mode</th><th>Command</th></tr>
<tr><td>Previleged EXEC</td><td>enable</td></tr>
<tr><td>Global Previleged mode</td><td>configure terminal</td></tr>
</table>

<h3>Using the built-in help</h3>
To access the help we can type <b>?</b> (question mark). Using ? sign on terminal will display all the particular available commands at that point in the router. 

[From LinkedIn Learning](https://www.linkedin.com/learning/learning-cisco-cli-router-configuration/)
