01 - Initial Server Access

\# Verify network configuration



root@ubuntu:~# ip addr



2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER\_UP>

&nbsp;   inet 192.168.231.131/24

\# Verify SSH service



root@ubuntu:~# systemctl status ssh



● ssh.service - OpenBSD Secure Shell server

&nbsp;    Loaded: loaded (/usr/lib/systemd/system/ssh.service)

&nbsp;    Active: active (running)

\# Verify SSH listening port



root@ubuntu:~# ss -tulnp | grep :22



LISTEN 0      128      0.0.0.0:22

LISTEN 0      128         \[::]:22

\# Test SSH connection from the client



PS C:\\Users\\user> ssh aymanserver@192.168.231.131



Welcome to Ubuntu 24.04 LTS

\# Verification



\[✓] SSH service is running

\[✓] Port 22 is listening

\[✓] Remote SSH connection established

\# Result



Phase 01 completed successfully.

Next: 02 - User Management

