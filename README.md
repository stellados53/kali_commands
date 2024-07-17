
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


- to check the information of the TARGETIP website  
```
http://whois.domaintools.com/
```
- to check which techonology is used in TARGETIP website  
```
http://toolbar.netcraft.com/site_report?url=
```

- which which website have same ipaddress  

>if we can hack into 1 we can hack all the other

```
https://www.robtex.com/ 
```  
- Using bing.com, search for `ip: [TARGETIP ip]`
<h3 align="center"> ... </h3> 



## Nmap Commands

| Scan Type |	Example Command |
| --- | --- |
 | ARP Scan  | 	 `sudo nmap -PR -sn MACHINE_IP/24` | 
ICMP Echo Scan |  	`sudo nmap -PE -sn MACHINE_IP/24` | 
ICMP Timestamp Scan |  	`sudo nmap -PP -sn MACHINE_IP/24` | 
ICMP Address Mask Scan |  	`sudo nmap -PM -sn MACHINE_IP/24` | 
TCP SYN Ping Scan |  	`sudo nmap -PS22,80,443 -sn MACHINE_IP/30` | 
TCP ACK Ping Scan |  	`sudo nmap -PA22,80,443 -sn MACHINE_IP/30` | 
UDP Ping Scan |  	`sudo nmap -PU53,161,162 -sn MACHINE_IP/30` | 

Remember to add `-sn` if you are only interested in host discovery without port-scanning. Omitting `-sn` will let Nmap default to port-scanning the live hosts.
 | Option |  	Purpose | 
  | -- | -- | 
 | -n |  	no DNS lookup | 
 | -R |  	reverse-DNS lookup for all hosts | 
 | -sn  | 	host discovery only | 

<h3 align="center"> ... </h3> 


## HYDRA

- A password cracking tool uses a syntax.
- For SSH - `sudo hydra -l <username> -P <full path to pass> MACHINE_IP -t 4 ssh`.
- for HYDRA `sudo hydra -l <username> -P <passlist.txt> ftp://MACHINE_IP`.
- Mostly the password files are saved in `/usr/share/wordlists/rockyou.txt`.

| Options | Purpose |
| - | - |
| -l | identify as username |
| -P | identify as passcode file directory |
| -t (optional) | USE threads for the execution |
| 4 (opt) | No. of threads to be used |
| ssh | Use ssh and access the target machine |

> After the ssh run the command `ssh <username>@<machineIP>`. this helps to access the target machine.

