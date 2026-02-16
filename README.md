# 4.Execution_of_NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure: 
To do this EXPERIMENT- follows these steps:
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
## Client

```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    ip = input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())

```

## Server

```
import socket
from pythonping import ping

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

c, addr = s.accept()

while True:
    try:
        hostname = c.recv(1024).decode()
        if not hostname:
            break
        result = ping(hostname, verbose=False)
        c.send(str(result).encode())
    except Exception:
        c.send("Not Found".encode())

c.close()
s.close()

```

## Tranceroute command

```
from scapy.all import *

target = ["www.google.com"]
result, unans = traceroute(target, maxttl=32)
print(result, unans)

```
## Output
## Client
<img width="567" height="37" alt="Screenshot 2026-02-16 193002" src="https://github.com/user-attachments/assets/558bfff4-ea46-47d6-a010-c0b1684acf52" />

## Server
<img width="652" height="196" alt="Screenshot 2026-02-16 192958" src="https://github.com/user-attachments/assets/6997a8bf-6920-4dfc-b0d2-5b2bef834162" />

## Tranceroute
<img width="940" height="581" alt="Screenshot 2026-02-16 193022" src="https://github.com/user-attachments/assets/b6d05a69-7b10-4a50-a8da-6e77aa722250" />

## Result
Thus Execution of Network commands Performed 
