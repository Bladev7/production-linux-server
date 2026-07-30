# 02 - User Management

Create a dedicated non-root administrative user with `sudo` privileges for daily server administration.

---

Create Administrative User

```console
root@aymanserver:~# adduser bladev
```

The command launches an interactive setup to create the user account, configure a password, and create the user's home directory.

---

Grant Administrative Privileges

```console
root@aymanserver:~# usermod -aG sudo bladev
```

---

Switch to the New User

```console
root@aymanserver:~# su - bladev

Password:

bladev@aymanserver:~$
```

---

Verify Current User

```console
bladev@aymanserver:~$ whoami

bladev
```

---

Verify User Information

```console
bladev@aymanserver:~$ id

uid=1000(bladev) gid=1000(bladev) groups=1000(bladev),4(adm),24(cdrom),27(sudo),30(dip),46(plugdev),110(lxd)
```

---

Verify Group Membership

```console
bladev@aymanserver:~$ groups

bladev adm cdrom sudo dip plugdev lxd
```

---

Verify Administrative Access

```console
bladev@aymanserver:~$ sudo whoami

[sudo] password for bladev:
root
```

---

Verification

✅ Non-root administrative user created.

✅ User belongs to the `sudo` group.

✅ Administrative privileges verified.

✅ Future server administration will be performed using the non-root account.

---

Next

→ 03 - SSH Hardening