\# 03 - Firewall Configuration



Configure a host-based firewall using UFW (Uncomplicated Firewall) to establish a secure baseline by blocking unsolicited incoming traffic while allowing only required services.



---



\## Verify UFW Installation



```console

bladev@aymanserver:~$ sudo apt install ufw



Reading package lists... Done

Building dependency tree... Done

Reading state information... Done

ufw is already the newest version (0.36.2-6).

ufw set to manually installed.

0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.

```



> \*\*Note\*\*

>

> UFW is included with Ubuntu by default. On a fresh Ubuntu Server installation, it is typically pre-installed but disabled. Running the installation command verifies that the package is installed and installs it only if it is missing.



---



\## Enable UFW Service



```console

bladev@aymanserver:~$ sudo systemctl enable ufw



Synchronizing state of ufw.service with SysV service script with /usr/lib/systemd/systemd-sysv-install.

Executing: /usr/lib/systemd/systemd-sysv-install enable ufw

```



---



\## Verify UFW Service



```console

bladev@aymanserver:~$ sudo systemctl status ufw



● ufw.service - Uncomplicated firewall

&nbsp;    Loaded: loaded (/usr/lib/systemd/system/ufw.service; enabled; preset: enabled)

&nbsp;    Active: active (exited)

&nbsp;      Docs: man:ufw(8)

&nbsp;   Process: 658 ExecStart=/lib/ufw/ufw-init start (code=exited, status=0/SUCCESS)

```



---



\## Verify Firewall Status



```console

bladev@aymanserver:~$ sudo ufw status



Status: inactive

```



---



\## Configure Default Policies



```console

bladev@aymanserver:~$ sudo ufw default deny incoming



Default incoming policy changed to 'deny'

(be sure to update your rules accordingly)

```



```console

bladev@aymanserver:~$ sudo ufw default allow outgoing



Default outgoing policy changed to 'allow'

(be sure to update your rules accordingly)

```



---



\## Allow SSH



```console

bladev@aymanserver:~$ sudo ufw allow OpenSSH



Rules updated

Rules updated (v6)

```



---



\## Enable SSH Rate Limiting



```console

bladev@aymanserver:~$ sudo ufw limit OpenSSH



Rules updated

Rules updated (v6)

```



---



\## Enable Firewall



```console

bladev@aymanserver:~$ sudo ufw enable



Command may disrupt existing ssh connections.

Proceed with operation (y|n)? y



Firewall is active and enabled on system startup

```



---



\## Verify Firewall Configuration



```console

bladev@aymanserver:~$ sudo ufw status verbose



Status: active

Logging: on (low)

Default: deny (incoming), allow (outgoing), disabled (routed)

New profiles: skip



To                         Action      From

--                         ------      ----

22/tcp                     ALLOW IN    Anywhere

22/tcp (OpenSSH)           LIMIT IN    Anywhere

22/tcp (v6)                ALLOW IN    Anywhere (v6)

22/tcp (OpenSSH (v6))      LIMIT IN    Anywhere (v6)

```



---



\## Verify Firewall Rules



```console

bladev@aymanserver:~$ sudo ufw status numbered



Status: active



\[ 1] 22/tcp                     ALLOW IN    Anywhere

\[ 2] 22/tcp (OpenSSH)           LIMIT IN    Anywhere

\[ 3] 22/tcp (v6)                ALLOW IN    Anywhere (v6)

\[ 4] 22/tcp (OpenSSH (v6))      LIMIT IN    Anywhere (v6)

```



---



\## Verification



\- ✅ UFW package verified.

\- ✅ UFW service enabled.

\- ✅ Firewall status verified.

\- ✅ Default incoming policy configured to \*\*DENY\*\*.

\- ✅ Default outgoing policy configured to \*\*ALLOW\*\*.

\- ✅ SSH access allowed.

\- ✅ SSH rate limiting enabled.

\- ✅ Firewall enabled.

\- ✅ Firewall configuration verified.



---



\## Next



→ 04 - System Updates

