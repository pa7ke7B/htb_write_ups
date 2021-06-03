# Recon

## nmap

```nmap -sC -sV -oA nmap/valentine 10.10.10.79```

- 22/tcp  open  ssh      OpenSSH 5.9p1 Debian 5ubuntu1.10 (Ubuntu Linux; protocol 2.0)
	- used to seeing 7.2 not 5.9
	- tells us its an old version
- 443/tcp open  ssl/http Apache httpd 2.2.22 ((Ubuntu))
	- used to seeing 2.4.18 not 2.2.22

![](Pasted%20image%2020210602213236.png)

![](Pasted%20image%2020210602213658.png)

![](Pasted%20image%2020210602213904.png)

## gobuster
