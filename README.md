<h1>Packet Tracer - Configuring Static Routes on Routers to Allow PCs to Ping Each Other</h1>

<p align="center">
This is the diagram of the network where I'll be configuring static routes on the routers to so PC1 and PC2 can successfully ping each other: <br/>
<img src="https://i.imgur.com/pQ7H4GN.png" height="80%" width="80%"/>
<br />
<br />
I'll first configure the static route for Router 1. To do this I'll access Router 1's CLI and enter Global Configuration mode from Priveleged Exec mode. Then I'll declare the static route the router should utilize with the command "ip route 192.168.3.0 255.255.255.0 192.168.12.2". "192.168.3.0 255.255.0" defines the destination prefix and subnet mask, or the network address for the LAN where PC2 is located. "192.168.12.2" defines the next hop that Router 1 will make, to Router 2's G0/0 interface, to reach LAN where PC2 is located.
<img src="https://i.imgur.com/y3LiizX.png" height="80%" width="80%"/>
<br />
<br />
By using the command "do show ip route" I can verify if the static route was successfully implemented. As one can see, the static IP has been succesfully implemented and we can even see the local route (L), the address configured on the interfaces, and the connected route (c), the network addresses which Router 1's interfaces are connected to.  
<img src="https://i.imgur.com/0CSFcWe.png" height="80%" width="80%"/>
<br />
<br />
By using the command "do show ip route" I can verify if the static route was successfully implemented. As one can see, the static IP has been succesfully implemented and we can even see the local route (L), the address configured on the interfaces, and the connected route (c), the network addresses which Router 1's interfaces are connected to.  
<img src="https://i.imgur.com/0CSFcWe.png" height="80%" width="80%"/>
<br />
<br />
</p>

