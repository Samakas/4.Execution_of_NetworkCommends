## 4. EXECUTION OF NETWORK COMMANDS
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## Program
### PING COMMAND:
### Client
```
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
### Server
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### TRACEROUTE COMMAND
```
from scapy.all import* 
target = ["www.google.com"] ![client3a](https://github.com/Samakas/4.Execution_of_NetworkCommends/assets/154731670/2ca51187-2778-4c6a-974f-5f10b708a42b)

result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output
### Client
![client4a](https://github.com/Samakas/4.Execution_of_NetworkCommends/assets/154731670/2bc2456a-e425-4448-8fb3-f5bf33c1b50f)
### Server
![server4a](https://github.com/Samakas/4.Execution_of_NetworkCommends/assets/154731670/53df9e87-3dd1-4a52-818b-8d2f3712e034)
### TRACEROUTE COMMAND
![tc](https://github.com/Samakas/4.Execution_of_NetworkCommends/assets/154731670/9e09b05c-4390-4d7a-aead-4cac6e668c06)

## Result :
Thus "Execution of Network commands" Performed successfully.
