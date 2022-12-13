# OSCP Methodology Cheatsheet

Taken from [here](https://falconspy.medium.com/oscp-developing-a-methodology-32f4ab471fd6)

## Port & Service Scanning

### nmap
```sh
# Default scripts and banner/service grabbing against the top common ports
nmap -sC -sV IP_ADDRESS

# Full port scan from port 1 to 65535
nmap -sC -sV -p- IP_ADDRESS

# Scan against top 20 most common UDP ports
nmap -sU -sV --top-ports 20 IP_ADDRESS

# Runs nmap scripts for vulnerability detection
nmap --script vuln IP_ADDRESS
```
### AutoRecon
https://github.com/Tib3rius/AutoRecon

## Web-related Recon

### Nikto
https://github.com/sullo/nikto

### dirsearch

### gobuster
```sh
gobuster -u <url> -w /opt/SecLists/Discovery/DNS/subdomains-top1million-110000.txt
```

### wfuzz
https://github.com/xmendez/wfuzz

## Exploitation

### searchsploit

https://www.exploit-db.com/documentation/Offsec-SearchSploit.pdf

## Privilege Escalation

### LinEnum
Scripted Local Linux Enumeration & Privilege Escalation Checks

### LinPrivChecker
https://github.com/linted/linuxprivchecker

### Linux Smart Enumeration
https://github.com/diego-treitos/linux-smart-enumeration

### PowerUp
```sh
powershell.exe -exec bypass -Command “& {Import-Module .\PowerUp.ps1; Invoke-AllChecks}”
```

### Powerless
https://github.com/gladiatx0r/Powerless

## Things to look for
* Process running as root/admin user
* Cracked password. Might just be the same for root/admin
* setuid binaries
* World Read/Write files
* Scheduled Tasks/Cronjobs that can be reconfigured
* User Paths
