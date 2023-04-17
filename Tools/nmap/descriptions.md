---

title: descriptions
layout: default
parent: nmap
grand_parent: Tools

---

[NMAP](https://nmap.org/)

## nmap states

*   `open` - application on a target machine is listening for connections/packets on this port
*   `closed` - server has no applications listening on a port
*   `filtered` - firewall/filter or something else is blocking a port, so nmap can't tell if it's opened or closed
*   `unfiltered` - port is responsive for nmap probes, but nmap can't decide if it opened or closed
