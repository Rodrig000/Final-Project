                                    By: Rodrigo Quiroz
# Network Forensic Analysis Report 
------------------------------------
## Time Thieves

At least two users on the network have been wasting time on YouTube. Usually, IT wouldn't pay much mind to the behavior, but it seems these people have created their own web server on the corporate network. So far, Security knows the following about these time thieves:

They have set up an Active Directory network
They are constantly watching videos on YouTube.
Their IP addresses are somewhere in the range 10.6.12.0/24

Inspect thenetwork traffic to complete the following report:
1. **_What is the domain name of the users' custom site?_**
* The Domain Name: **Frank-n-Tead-DC.frand-n-ted.com**
* Filter used in Wireshark: **ip.addr==10.6.12.0/24**
* Screenshot:![alt text](https://github.com/Rodrig000/Project1Repository/blob/main/images/results.jpg)

2. **_What is the IP address of the Domain Controller (DC) of the AD network?_**
* IP address is **10.6.12.12 (Frank-n-Ted-DC.frank-n-ted.com)**
* Screenshot:![alt text](https://github.com/Rodrig000/Project1Repository/blob/main/images/Frank.png)

3. **_What is the name of the malware downloaded to the 10.6.12.203 machine?_**
* **Malware file: june11.dll**
* Screenshot:![alt text](https://github.com/Rodrig000/Project1Repository/blob/main/images/request%20meth.jpg)
Once you have found the file, export it to your Kali machine's desktop.

4. **_Upload the file to VirusTotal.com._**

5. **_What kind of malware is this classified as?_** 
* **This malware is classified as a Trojan**
* Screenshot:![alt text](https://github.com/Rodrig000/Project1Repository/blob/main/images/Screenshot%202022-08-23%20175758.jpg)

## Vulnerable Windows Machine


1. **_Find the following information about the infected Windows machine:_**
* Host name: **ROTTERDAM-PC**
* IP address: **172.16.4.205** 
* MAC address: **00:59:07:b0:63:a4**

2. **_What is the username of the Windows user whose computer is infected?_**
* Filter used in Wireshark: **ip.src==172.16.4.205 and kerberos.CNameString**
3. What are the IP addresses used in the actual infection traffic?
* **172.16.4.205 and 185.243.115.84 were the IPs with the highest amount of packet traffic**
