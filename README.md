<h1>BGP_HIJACKING_Demo_Using_Mininet</h1>

<h2>What is BGP(Border Gateway Protocol) Hijacking?</h2>


BGP hijacking is a malicious attack on the Border Gateway Protocol (BGP), the system responsible for routing internet traffic between autonomous systems (ASes). In this attack, a malicious actor falsely advertises ownership of IP address ranges that do not belong to them, causing data intended for the legitimate IP owner to be rerouted through the attacker’s network. This can lead to various harmful outcomes, including traffic interception, data theft, or denial of service. BGP hijacking exploits the trust-based nature of BGP, which assumes that all routing announcements are accurate, making it a significant security threat to the internet infrastructure.

<h2>Instructions to run code</h2>
<h3>1.Install <a href="https://github.com/mininet/mininet/releases/download/2.3.0/mininet-2.3.0-210211-ubuntu-20.04.1-legacy-server-amd64-ovf.zip">Mininet</a></h3>
<h3>2.Install  <a href="https://www.youtube.com/watch?v=3jj6X3OkujQ">GUI</a></h3>
<h3>3.Clone the Repository</h3>
<h3>4.Run the following commands</h3>
 &nbsp  mininet@mininet-vm:$ cd BGP_Path_Hijack/<br>
 &nbsp # replace paths in 'bgp.py' in the lines 147 and 149 ,also in `start_rogue.sh` and 'stop_rogue.sh'<br>
 &nbsp mininet@mininet-vm:$ sudo python3 bgp.py<br>
 &nbsp # new termial window, connect to S1 router, passwd is "en", type twice with [enter]<br>
 &nbsp mininet@mininet-vm:$ ./connect.sh<br>
 &nbsp # bgpd-S1# show ip bgp<br>
 &nbsp # new another window, test web service<br>
 &nbsp mininet@mininet-vm:$ ./website.sh<br>
 &nbsp # new another window, start roguing AS<br>
 &nbsp mininet@mininet-vm:$ ./start_rogue.sh<br>
 &nbsp # bgpd-S1# show ip bgp<br>
 &nbsp # check the output in `website.sh` window<br>
 &nbsp mininet@mininet-vm:$ ./stop_rogue.sh<br>
<br>
 <b>Note:</b>Make sure that you have installed FRR (free range routing) by running <b>sudo apt-get install frr</b> ,also enable and start frr by running <b>systemctl enable frr</b> and <b>systemctl start frr.</b>

