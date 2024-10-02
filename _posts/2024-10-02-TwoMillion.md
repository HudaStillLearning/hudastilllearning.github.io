---
title: HackTheBox - TwoMillion
date: 2024-10-02 09:31:00 +0700
categories:
  - HackTheBox
  - Machines
tags:
  - easy
---
![Machine Info Card](/assets/img/hackthebox/machines/easy/twomillion/TwoMillion.png)

## Enumeration
### Nmap
```zsh
# Nmap 7.95 scan initiated Wed Oct  2 09:22:43 2024 as: nmap -sCV -T4 -oN nmap.txt -vv 10.10.11.221
Nmap scan report for jsn.jaringanku (10.10.11.221)
Host is up, received syn-ack (0.27s latency).
Scanned at 2024-10-02 09:22:43 WIB for 45s
Not shown: 997 closed tcp ports (conn-refused)
PORT   STATE    SERVICE     REASON      VERSION
3/tcp  filtered compressnet no-response
22/tcp open     ssh         syn-ack     OpenSSH 8.9p1 Ubuntu 3ubuntu0.1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   256 3e:ea:45:4b:c5:d1:6d:6f:e2:d4:d1:3b:0a:3d:a9:4f (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBJ+m7rYl1vRtnm789pH3IRhxI4CNCANVj+N5kovboNzcw9vHsBwvPX3KYA3cxGbKiA0VqbKRpOHnpsMuHEXEVJc=
|   256 64:cc:75:de:4a:e6:a5:b4:73:eb:3f:1b:cf:b4:e3:94 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIOtuEdoYxTohG80Bo6YCqSzUY9+qbnAFnhsk4yAZNqhM
80/tcp open     http        syn-ack     nginx
|_http-title: Did not follow redirect to http://2million.htb/
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Wed Oct  2 09:23:28 2024 -- 1 IP address (1 host up) scanned in 45.85 seconds
```
add `<IP> 2million.htb` to `/etc/hosts`
```zsh
sudo vim /etc/hosts 
# or
echo "<IP> 2million.htb" | sudo tee -a /etc/hosts
```
go to the website
![Browser](/assets/img/hackthebox/machines/easy/twomillion/web-page.png)
click join and we are redirected to /invite
![Browser](/assets/img/hackthebox/machines/easy/twomillion/web-invite.png)