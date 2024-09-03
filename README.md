<h1>BGP_HIJACKING_Using_Mininet</h1>

<h3>1.Install <a href="(https://github.com/mininet/mininet/releases/download/2.3.0/mininet-2.3.0-210211-ubuntu-20.04.1-legacy-server-amd64-ovf.zip)">Mininet</a></h3>
<h3>2.Run the following commands</h3>

```
mininet@mininet-vm:$ cd BGP_Path_Hijack/
# replace paths in bgp.py in the lines 147 and 149
mininet@mininet-vm:$ sudo python3 bgp.py
# new termial window, connect to S1 router, passwd is "en", type twice with [enter]
mininet@mininet-vm:$ ./connect.sh
bgpd-S1# show ip bgp
# new another window, test web service
mininet@mininet-vm:$ ./website.sh
# new another window, start roguing AS
mininet@mininet-vm:$ ./start_rogue.sh
# check the output in `website.sh` windows
mininet@mininet-vm:$ ./stop_rogue.sh
```
