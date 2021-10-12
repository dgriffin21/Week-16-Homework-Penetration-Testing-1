## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is: **Karl Fitzgerald**

- How can this information be helpful to an attacker: **By using Karl as a target to gain access to the maximum amount of company info avaliable.** 


#### Step 2: DNS and Domain Discovery

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located: **Sunnyvale, CA**

  2. What is the NetRange IP address:**65.61.137.64 - 65.61.137.127**

  3. What is the company they use to store their infrastructure: **Rackspace Backbone Engineering**

  4. What is the IP address of the DNS server:**65.61.137.117**


#### Step 3: Shodan

- What open ports and running services did Shodan find: **Ports: 80, 443, 8080** **Services: Apache Tomcat, Coyote JSP Engine**

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 
- Set the source to `demo.testfire.net`. 
- Run the module. 

Is Altoro Mutual vulnerable to XSS: **Yes, it is the only vulnerablility ** 


### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: **nmap -T4 -A 192.168.0.10**
 
- Bonus command to output results into a new text file named `zenmapscan.txt`:

- Zenmap vulnerability script command:
  **nmap --script samba-vuln-cve-2012-1182 192.168.0.10**


- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability:
  **(Samba) SMB 3**

  2. Why is it dangerous:
  3.**Samba versions 3.6.3 and all  previous are affected by a vulnerability that allows remote code execution as the “root” user from an anonymous connections.

  3. What mitigation strategies can you recommendations for the client to protect their server:
  **Block all inbound SMB traffic by using the Windows Defender Firewall to prevent remote connections from malicious or compromised devices, for Windows clients and servers that do not host SMB shares.**
---
