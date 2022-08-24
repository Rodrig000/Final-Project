                                 By: Rodrigo Quiroz
# Red Team: Summary of Operations
----------------------------------
### Table of Contents

* Exposed Services
* Critical Vulnerabilities
* Exploitation


### Exposed Services

* Nmap scan results for each machine reveal the below services and OS details:
* $ nmap -sV 192.168.1.110
* ![alt text](https://github.com/Rodrig000/Project1Repository/blob/main/images/rl%20nmap%20scan.jpg)
This scan identifies the services below as potential points of entry:

### Target 1
* **_Port 22/TCP Open SSH_**
* **_Port 80/TCP Open HTTP_**
* **_Port 111/TCP Open rcpbind_**
* **_Port 139/TCP Open netbios_**
* **_Port 445/TCP Open netbios_**



TODO: Fill out the list below. Include severity, and CVE numbers, if possible.
The following vulnerabilities were identified on each target:

Target 1

List of
Critical
Vulnerabilities



TODO: Include vulnerability scan results to prove the identified vulnerabilities.

Exploitation
TODO: Fill out the details below. Include screenshots where possible.
The Red Team was able to penetrate Target 1 and retrieve the following confidential data:

Target 1


flag1.txt: TODO: Insert flag1.txt hash value


Exploit Used

TODO: Identify the exploit used
TODO: Include the command run





flag2.txt: TODO: Insert flag2.txt hash value


Exploit Used

TODO: Identify the exploit used
TODO: Include the command run
