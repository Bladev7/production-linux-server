\# 01 - Initial Server Access



> Verify that the Ubuntu Server is operational and accessible remotely before applying any security hardening.



---



\## Check Server IP Address



```console

root@ubuntu:~# ip addr

```



Identify the server's IPv4 address.



---



\## Verify SSH Service



```console

root@ubuntu:~# systemctl status ssh

```



Expected:



```text

Active: active (running)

```



---



\## Verify SSH Listening Port



```console

root@ubuntu:~# ss -tulnp | grep :22

```



Expected:



```text

LISTEN ... :22

```



---



\## Test Remote SSH Connection



```console

PS C:\\Users\\user> ssh <username>@<server-ip>

```



Expected:



```text

Welcome to Ubuntu

```



---



\## Verification



\- \[x] SSH service is running.

\- \[x] SSH is listening on TCP port 22.

\- \[x] Remote SSH connection established successfully.



---



\## Security Notes



\- Initial server connectivity verified.

\- No security hardening has been applied yet.

\- Ready for Phase 02.



---



✓ Phase 01 Completed

