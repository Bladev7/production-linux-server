\# 02 - User Management



Create a dedicated non-root administrative user with `sudo` privileges for daily server administration.



---



\## Create Administrative User



```console

root@aymanserver:~# adduser bladev



Adding user `bladev' ...

Adding new group `bladev' (1000) ...

Adding new user `bladev' (1000) with group `bladev' ...

Creating home directory `/home/bladev' ...

Copying files from `/etc/skel' ...

New password:

Retype new password:

passwd: password updated successfully

Changing the user information for bladev

Enter the new value, or press ENTER for the default

&nbsp;   Full Name \[]:

&nbsp;   Room Number \[]:

&nbsp;   Work Phone \[]:

&nbsp;   Home Phone \[]:

&nbsp;   Other \[]:

Is the information correct? \[Y/n] y

```



---



\## Grant Administrative Privileges



```console

root@aymanserver:~# usermod -aG sudo bladev

```



---



\## Switch to the New User



```console

root@aymanserver:~# su - bladev



Password:



bladev@aymanserver:~$

```



---



\## Verify Current User



```console

bladev@aymanserver:~$ whoami

```



> \*\*(We'll replace this with your real output.)\*\*



---



\## Verify User Information



```console

bladev@aymanserver:~$ id

```



> \*\*(We'll replace this with your real output.)\*\*



---



\## Verify Group Membership



```console

bladev@aymanserver:~$ groups

```



> \*\*(We'll replace this with your real output.)\*\*



---



\## Verify Administrative Access



```console

bladev@aymanserver:~$ sudo whoami

```



> \*\*(We'll replace this with your real output.)\*\*



---



\## Verification



\- ✅ Non-root administrative user created.

\- ✅ User added to the `sudo` group.

\- ✅ Administrative privileges verified.

\- ✅ Server administration performed using the non-root account.



---



\## Next



→ \*\*03 - SSH Hardening\*\*

