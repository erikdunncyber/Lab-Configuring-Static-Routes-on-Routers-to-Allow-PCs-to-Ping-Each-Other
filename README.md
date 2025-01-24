<h1>Packet Tracer - Configuring Static Routes on Routers to Allow PCs to Ping Each Other</h1>

<p align="center">
This is the diagram of the network where I'll be configuring static routes on the routers to so PC1 and PC2 can successfully ping each other: <br/>
<img src="https://i.imgur.com/pQ7H4GN.png" height="80%" width="80%"/>
<br />
<br />
I'll first configure the static route for Router 1. To do this I'll access Router 1's CLI and enter Global Configuration mode from Priveleged Exec mode. Then I'll declare the static route the router should utilize with the command "ip route 192.168.3.0 255.255.255.0 192.168.12.2". "192.168.3.0 255.255.0" defines the destination prefix and subnet mask, or the network address for the LAN where PC2 is located. "192.168.12.2" defines the next hop that Router 1 will make, to Router 2's G0/0 interface, to reach LAN where PC2 is located: <br/>
<img src="https://i.imgur.com/y3LiizX.png" height="80%" width="80%"/>
<br />
<br />
By using the command "do show ip route" I can verify if the static route was successfully implemented. As one can see, the static IP has been succesfully implemented and we can even see the local route (L), the address configured on the interfaces, and the connected route (c), the network addresses which Router 1's interfaces are connected to: <br/>  
<img src="https://i.imgur.com/0CSFcWe.png" height="80%" width="80%"/>
<br />
<br />
Now I'll move on to setting the static route for Router 2. Through Global Configuration mode on Router 2's CLI, I'll set the static route using the commands "ip route 192.168.1.0 255.255.255.0 192.168.12.1" and "ip route 192.168.3.0 255.255.255.0 192.168.13.3". This first command sets the static route towards network address where PC 1 is located and second command sets the static route towards the address where PC 2 is located: <br/>  
<img src="https://i.imgur.com/rs8if6b.png" height="80%" width="80%"/>
<br />
<br />
Once again, I can verify if the changes went through using the "do show ip route" command. Everthing appears to be in order: <br/>  
<img src="https://i.imgur.com/mGvggJh.png" height="80%" width="80%"/>
<br />
<br />
Moving on to Router 3, I'll configure the route to 192.168.1.0/24 using the command "ip route 192.168.1.0 255.255.255.0 192.168.13.2": <br/>  
<img src="https://i.imgur.com/vVKhDBc.png" height="80%" width="80%"/>
<br />
<br />
Judging by the ip route table, the static route seems to have been set correctly: <br/>  
<img src="https://i.imgur.com/e8jyjg6.png" height="80%" width="80%"/>
<br />
<br />
Now I'll attempt to Ping PC2 using PC1. Through PC1's command prompt I use the command "ping 192.168.3.1" and it shows that 4/4 packets were successfully sent and recieved. This means that I was succesfully able to configure the static routing between the devices on each network to allow PC1 and PC2 to communicate with each other: <br/>  
<img src="https://i.imgur.com/4KlYEDw.png" height="80%" width="80%"/>
<br />
<br />
</p>

