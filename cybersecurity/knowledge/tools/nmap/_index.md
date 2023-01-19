---
title: Nmap
---

`nmap` (Network Mapper) is an industry standard tool for mapping networks, identifying live hosts and discovering running services.

## Scripting engine

Nmap’s _scripting engine_ can further extend its functionality, from fingerprinting services to exploiting vulnerabilities.

## Enumerating hosts

We mentioned the different *techniques* we can use for scanning in Task 1.

Before we scan the live targets, we need to specify them. Generally, we provide a list, a range, or a subnet. Examples of target specification are:

- list: `10.11.12.15 scanme.nmap.org example.com` - will scan 3 IP addresses.
- range: `10.11.12.15-20` - 6 IP addresses
  - `nmap -sL -n 10.10.0-255.101-125` - 6400 IPs lol
- subnet: `10.11.12.15/30` - 4 IP addresses
- list of targets: `nmap -iL list_of_hosts.txt` - as many as in the list

`nmap -sL list_of_hosts.txt` will give a detailed lists of hosts to scan without actually scanning them with reverse-DNS resolution on all targets to obtain their names (unless blocked with `-n`).

## Discovering live hosts

We will leverage the protocols to discover the live hosts.

- [[networks/ARP]] from [[private/cybersec/networking/OSI Model#Layer 2: Data Link|Data-link Layer]]
  - [[host-discovery-using-arp]]
- [[cybersecurity/knowledge/glossary/ICMP]] from [[private/cybersec/networking/OSI Model#Layer 3: Network|Network Layer]]
  - [[host-discovery-using-icmp]]
- TCP from [[private/cybersec/networking/OSI Model#Layer 4: Transport|Transport Layer]]
- UDP from [[private/cybersec/networking/OSI Model#Layer 4: Transport|Transport Layer]]

Although TCP and UDP are transport layers, for network scanning purposes, a scanner can send a **specially-crafted** packet to common TCP or UDP ports to check whether the target will respond. This method is efficient, especially when `ICMP Echo` is blocked.

## Approaches to discover hosts

When no host discovery options are provided, Nmap follows the following approaches to discover live hosts:

1.  When a *privileged* user tries to scan targets on a local network (_Ethernet_), Nmap uses [[networks/ARP]] requests. A privileged user is `root` or a user who belongs to [[sudoers]].
2.  When a *privileged* user tries to scan targets outside the local network, Nmap uses [[cybersecurity/knowledge/glossary/ICMP]] `echo` requests, [[TCP]] ACK (Acknowledge) to port 80, TCP SYN (Synchronize) to port 443, and ICMP `timestamp` request.
3.  When an *unprivileged* user tries to scan targets outside the local network, Nmap resorts to a TCP 3-way handshake by sending SYN packets to ports 80 and 443.

Nmap, by default, uses a ping scan to find live hosts, then proceeds to scan live hosts only.

If you want to use Nmap to discover online hosts without port-scanning the live systems, we can issue:

```sh
nmap -sn TARGETS
```

## Types of ICMP Requests

We can make Nmap to use ICMP requests with these flags:

- `-PP` - timestamp
- `-PM` - address mask
- `-PE` - echo
