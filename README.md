
# kali linux commands
| usage | command |
| --- | --- |
| prints current working directry, uses to redirect to open a file | `pwd`  |
| list all files | `ls` |
| list of all files in the directory with details | `ls -l` |
| open a folder | `cd` |
| previous folder | `..` | 
| prints descrption of a function | `man` |
| create a file directory | `mkdir (filename)` |
| copy paste a file or folder | `cp (from filelocation) (to filelocation)` |
| Delete a file | `rm -rf` |
| to create a file |  `touch <filename>` |
| to find a file in kali linux | `find -name <filename>` |
| to find how many lines in the file | `wc -l <filename>` |
| to find a term in the file | `grep "<term>" <filename>` |
| update tools | `sudo apt-get update` |
| upgrade tools | `sudo apt-get upgrade` |
| upgrade kali linux | `sudo apt upgrade` | 
| update kali linux | `sudo apt update` |
| run 2 commands concurently |  `ls;pwd` or `ls && pwd` |
| run the 2nd command directly by neglecting the first commands | `ls (shift+\) pwd` |
| display the contents of the file | `cat <filedirectory>` |
<h3 align="center"> ... </h3>  

## check IP address


- to check the information of the target website  
```
http://whois.domaintools.com/
```
- to check which techonology is used in target website  
```
http://toolbar.netcraft.com/site_report?url=
```

- which which website have same ipaddress  

>if we can hack into 1 we can hack all the other

```
https://www.robtex.com/ 
```  
- Using bing.com, search for `ip: [target ip]`
<h3 align="center"> ... </h3> 

## Nmap Commands
> `-sn` is to retrieve only the open ports.

### ARP
| usage | command |
| --- | --- |
| Scan ARP protocol IPs |  `sudo nmap -PR -sn [TARGET (OR) MACHINEIP/24]` <br> `sudo arpscan [TARGET (or) MACHINEIP/24]` |

### ICMP

| usage | command |
| --- | --- |
| scans based on TIMESTAMP | `sudo nmap -PP -sn [TARGET (OR) MACHINEIP/24]` |
| Scans based on ECHO | `sudo nmap -PE -sn [TARGET (OR) MACHINEIP/24]` |
| Scans based on ADDRESS MARK | `sudo nmap -PM -sn [TARGET (OR) MACHINEIP/24]` |

### TCP AND UDP

> `-p` is to scan only the port number.

| usage | command |
| --- | --- |
| TCP for which follows 3way handshake <br> (uprevilaged user[non-root user]) | `sudo nmap -PS -sn [TARGET (OR) MACHINEIP/24 -p80,443,8080,etc]` |
| TCP doesn't follow 3way handshake <br> (previlaged User[root or sudoer user]) | `sudo nmap -PA -sn [TARGET (OR) MACHINEIP/24]` |
| UDP Protocols | `sudo nmap -PU -sn [TARGET (OR) MACHINEIP/24]` |





