<h1>BGP_HIJACKING_Demo_Using_Mininet</h1>

<h2>What is BGP(Border Gateway Protocol) Hijacking</h2>


<h6>BGP hijacking is a malicious attack on the Border Gateway Protocol (BGP), the system responsible for routing internet traffic between autonomous systems (ASes). In this attack, a malicious actor falsely advertises ownership of IP address ranges that do not belong to them, causing data intended for the legitimate IP owner to be rerouted through the attacker’s network. This can lead to various harmful outcomes, including traffic interception, data theft, or denial of service. BGP hijacking exploits the trust-based nature of BGP, which assumes that all routing announcements are accurate, making it a significant security threat to the internet infrastructure.</h6>

<h2>Instructions</h2>
<h3>1.Install <a href="https://github.com/mininet/mininet/releases/download/2.3.0/mininet-2.3.0-210211-ubuntu-20.04.1-legacy-server-amd64-ovf.zip">Mininet</a></h3>
<h3>2.Install  <a href="https://www.youtube.com/watch?v=3jj6X3OkujQ">GUI</a></h3>
<h3>3.Clone the Repo</h3>
<h3>4.Run the following commands</h3>
```
mininet@mininet-vm:$ cd BGP_Path_Hijack/<br>
# replace paths in bgp.py in the lines 147 and 149<br>
mininet@mininet-vm:$ sudo python3 bgp.py<br>
# new termial window, connect to S1 router, passwd is "en", type twice with [enter]<br>
mininet@mininet-vm:$ ./connect.sh<br>
bgpd-S1# show ip bgp<br>
# new another window, test web service<br>
mininet@mininet-vm:$ ./website.sh<br>
# new another window, start roguing AS<br>
mininet@mininet-vm:$ ./start_rogue.sh<br>
# check the output in `website.sh` windows<br>
mininet@mininet-vm:$ ./stop_rogue.sh
```
