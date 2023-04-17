---

title: cheetsheet
layout: default
parent: nmap
grand_parent: Tools

---

```shell
# scan the most common 1000 ports for each protocol
nmap <target>
```

```shell
# scan port
nmap -p 80 <target>
```

```shell
# scan ports range
nmap -p 1-65535 <target>
```

```shell
# scan ports of certain protocol
# U - UDP, T - TCP, S - SCTP, P - IP
# https://nmap.org/book/man-port-specification.html
nmap -sU -p U:1,2-10 <target>
nmap -p T:1,2-10 <target>
nmap -p S:1,2-10 <target>
nmap -p P:1,2-10 <target>
```

```shell
# ping scan
# can be usefull if need to detect which IP address is active
# https://nmap.org/book/host-discovery.html

# single host can be pinged
nmap -sn 10.11.12.13

# but usually it's more useful with address space
nmap -sn 10.11.12.0/24
```

```shell
# scan list of targets
# https://nmap.org/book/man-target-specification.html
nmap -il filename.txt
```

```shell
# scan with info which service started on which port
nmap -sv <target>

# output example:
#PORT   STATE SERVICE VERSION
#22/tcp open  ssh   OpenSSH 8.9p1 Ubuntu 3ubuntu0.1 (Ubuntu Linux; protocol #2.0)
#443/tcp closed https
#Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel
```

```shell
# scan with OS detection
nmap -O <target>

# output example:
#Device type: general purpose|storage-misc|firewall
#Running (JUST GUESSING): Linux 2.6.X|4.X|3.X (88%), Synology DiskStation Manager #5.X (86%), WatchGuard Fireware 11.X (86%), FreeBSD 6.X (85%)
#OS CPE: cpe:/o:linux:linux_kernel:2.6.32 cpe:/o:linux:linux_kernel:4.0 cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel cpe:/a:synology:diskstation_manager:5.1 cpe:/o:watchguard:fireware:11.8 cpe:/o:freebsd:freebsd:6.2
#Aggressive OS guesses: Linux 2.6.32 (88%), Linux 4.0 (86%), Linux 2.6.39 (86%), Linux 3.10 - 3.12 (86%), Linux 3.4 (86%), Linux 3.5 (86%), Linux 4.2 (86%), Linux 4.4 (86%), Synology DiskStation Manager 5.1 (86%), WatchGuard Fireware 11.8 (86%)
#No exact OS matches for host (test conditions non-ideal)
```
