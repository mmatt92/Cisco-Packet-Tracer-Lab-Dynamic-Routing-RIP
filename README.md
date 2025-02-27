<h1>Cisco Packet Tracer Lab/Dynamic Routing/RIP</h1>



<h2>Description</h2>

This lab will demonstrate how to setup a dynamic network using Routing Information Protocol (RIP). I will be using the initial network configuration from my static lab and changing the router settings. 
<br />


<h2>Utilities Used</h2>
 
- <b>Cisco Packet Tracer</b>

<h2>Environments Used </h2>

- <b>Windows 11</b> 

<h2>Network Map</h2>

<p align="center">
This diagram includes the IP networks and ports used for the following lab: <br/>
<img src="https://imgur.com/vk68kin.png" height="80%" width="80%" alt="Download from the browser"/>
<br />
<br />
Open Packet Tracer for new project:  <br/>
<img src="https://imgur.com/KC13ynw.png" height="80%" width="80%" alt="Open Packet Tracer for New Project"/>
<br />
<br />
Starting network (Please reference static lab for initial setup):  <br/>
<img src="https://imgur.com/ESpaXu9.png" height="80%" width="80%" alt="Start network"/>
<br />
<br />
Click on NY router to verify current connections in CLI :  <br/>
<img src="https://imgur.com/B0DGl2A.png" height="80%" width="80%" alt="NY router to verify current connections"/>
<br />
<br />
In the CLI. Enter, type "en" (enable) enter, "show ip route" enter. Notice the router only sees 192.168.10.0 and 192.168.20.0:  <br/>
<img src="https://imgur.com/Cjw1tw4.png" height="80%" width="80%" alt="NY router to verify current connections"/>
<br />
<br />
Click on LA router to verify current connection in CLI:  <br/>
<img src="https://imgur.com/v61V2Jz.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
In the CLI. Enter, type "en" (enable) enter, "show ip route" enter. Notice the router only sees 192.168.20.0 and 192.168.30.0:  <br/>
<img src="https://imgur.com/CWnXfhX.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Now to begin the process of configuring the routers to broadcast their ip using RIP starting with NY router in the CLI. Type "en" enter, "conf t" enter, "router rip" enter, "version 2" enter, "network 192.168.10.0" enter, "network 192.168.20.0" enter, "exit" enter:  <br/>
<img src="https://imgur.com/kUxllsT.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
And repeat the same commands for the LA ip addresses in CLI. Type "en" enter, "conf t" enter, "router rip" enter, "version 2" enter, "network 192.168.20.0" enter, "network 192.168.30.0" enter, "exit" enter:  <br/>
<img src="https://imgur.com/Uw9bCzM.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Now while in the LA router type "do sh ip route" enter:  <br/>
<img src="https://imgur.com/c8IJJnW.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Notice now how the LA router can see network 192.168.10.0 via 192.168.20.1 on port g0/0 on the NY router:  <br/>
<img src="https://imgur.com/wXS9HEf.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Also back in the NY router. Type "do sh ip route" enter. It shows that it can now see network 192.168.30.0 via 192.168.20.2 on port g0/0 on the LA router:  <br/>
<img src="https://imgur.com/bdag56s.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Next try to ping from PC1:  <br/>
<img src="https://imgur.com/ylgScOK.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Click on PC1. Desktop. Then Command Prompt:  <br/>
<img src="https://imgur.com/YHwyiR5.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Type "ping 192.168.30.1" enter. This will be port g0/1 on the LA router. Connection is successful:  <br/>
<img src="https://imgur.com/SvToyx6.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Now type "ping 192.168.30.10" enter. This will ping PC2. Connection is successful:  <br/>
<img src="https://imgur.com/YpjHDcI.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Next try to ping from PC2:  <br/>
<img src="https://imgur.com/MpDimo8.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Click on PC2. Desktop. Then Command Prompt:  <br/>
<img src="https://imgur.com/5hZ086f.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
Type "ping 192.168.10.10" enter. This will ping PC1. Connection is successful:  <br/>
<img src="https://imgur.com/TqF8TlM.png" height="80%" width="80%" alt="LA router to verify current connections"/>
<br />
<br />
End of lab:
</p>
