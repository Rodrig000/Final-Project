                                   By Rodrigo Quiroz
# Blue Team: Summary of Operations
-----------------------------
### Table of Contents

* Network Topology
* Description of Targets
* Monitoring the Targets
* Patterns of Traffic & Behavior
* Suggestions for Going Further

#### Network Topology
![alert_text](https://github.com/Rodrig000/Project1Repository/blob/main/images/topology.jpg)

**The following machines were identified on the network:**

**_Kali_**


* Operating System: **Debian Kali**

* Purpose: **Attacking Machine**

* IP Address: **192.168.1.90**


**_ELK_**


* Operating System: **Ubuntu**

* Purpose: **Elasticsearch & Kibana Stack**

* IP Address: **192.168.1.110**

**_Capstone_**

* Operating System: **Ubuntu**
* Purpose: **Vulnerable Web Server recording logs**
* IP Address: **192.168.1.105**

**_Target 1_**

* Operating System: **Debian GNU/Linux8**

* Purpose: **WordPress Host**

* IP Address: **192.168.1.110**




**Description of Targets**

* The target of this attack was: **Target 1 (192.168.1.110)**
* Target 1 is an Apache web server and has SSH enabled, so ports 80 and 22 are possible ports of entry for attackers. As such, the following alerts have been implemented:

Monitoring the Targets
Traffic to these services should be carefully monitored. To this end, we have implemented the alerts below:

**_Excessive HTTP Errors_**
 
* Metric: **WHEN count() GROUPED OVER top 5 'http.response.status_code'**
* Threshold: **is above 400**
* Vulnerability Mitigated: **Enumeration**
* Reliability: **moderate considering false positives**

**_HTTP Request Size Monitor_**

* Metric: **WHEN sum() of http.resquest.byte OVER all documents**
* Threshold: **is above 3500**
* Vulnerability Mitigated: **XSS**
* Reliability: **moderate considering false positives**

**_CPU Usage Monitor_**

* Metric: **WHEN max() OF system.process.cpu.total.pct OVER all documents**
* Threshold: **Is above 0.5**
* Vulnerability Mitigated: **Malicious software (Viruses)**
* Reliability: **High considering it helps CPU improve storage**
