# 01 - Initial Server Access

> Verify that the Ubuntu Server is operational and accessible remotely before applying any security hardening.

## Check Server IP Address

```console
aymanserver:~$ ip -4 addr

2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP>
    inet 192.168.231.131/24 brd 192.168.231.255 scope global dynamic enp0s3
```

## Verify SSH Service

```console
aymanserver:~$ systemctl status ssh --no-pager

● ssh.service - OpenBSD Secure Shell server
     Loaded: loaded (...)
     Active: active (running)
       Docs: man:sshd(8)
```

## Verify SSH Listening Port

```console
aymanserver:~$ ss -tulnp | grep :22

tcp   LISTEN 0      128      0.0.0.0:22      0.0.0.0:*      users:(("sshd",pid=...,fd=3))
tcp   LISTEN 0      128         [::]:22         [::]:*      users:(("sshd",pid=...,fd=4))
```

## Test Remote SSH Connection

```console
PS C:\Users\user> ssh aymanserver@192.168.231.131

Welcome to Ubuntu 24.04 LTS (GNU/Linux ...)
...
Last login: ...
aymanserver:~$
```

## Verification

- ✅ SSH service is active.
- ✅ SSH is listening on TCP port 22.
- ✅ Remote administration verified.

## Next

→ 02 - User Management