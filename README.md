# DHCP + DNS Dynamic Configuration Project

This project integrates an ISC DHCP server with a BIND9 DNS server to provide dynamic DNS updates (DDNS).  
It was developed using **Debian** virtual machines managed with **Vagrant**.

## 🧱 Infrastructure
| Machine | Role | IP Address | Description |
|----------|------|-------------|--------------|
| server-dns | DNS Server (BIND9) | 192.168.58.10 | Handles forward and reverse zones with DDNS |
| server-dhcp | DHCP Server (ISC) | 192.168.58.11 | Assigns IPs dynamically and updates DNS |
| client | DHCP Client | 192.168.58.100+ | Receives IP via DHCP and updates DNS dynamically |

## 🧪 Tests Performed
- Client receives IP from DHCP server.
- DNS zones updated dynamically with client hostname and IP.
- Direct and reverse resolution verified using `dig`.

## 🧰 Useful Commands
| Purpose | Command |
|----------|----------|
| Check DHCP syntax | `sudo dhcpd -t` |
| Restart DHCP service | `sudo systemctl restart isc-dhcp-server` |
| Restart DNS service | `sudo systemctl restart bind9` |
| Check logs | `sudo journalctl -u isc-dhcp-server` or `sudo tail -f /var/log/syslog` |
| Test DNS resolution | `dig client.example.test` |
| Test reverse lookup | `dig -x 192.168.58.100` |

---

📘 *Created by Álvaro Mateos Gálvez — Networking Practice (DHCP-DNS Dynamic Updates).*
