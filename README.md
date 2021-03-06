# week16
## Week 16 Homework Submission File: Penetration Testing 1

#### Step 1: Google Dorking


- Using Google, can you identify who the Chief Executive Officer of Altoro Mutual is:
  - Karl Fitzgerald

- How can this information be helpful to an attacker:
  - Definitely during recon for social engineering, phishing.


#### Step 2: DNS and Domain Discovery

Enter the IP address for `demo.testfire.net` into Domain Dossier and answer the following questions based on the results:

  1. Where is the company located:
    - Sunnyvale, CA

  2. What is the NetRange IP address:
    - 65.61.137.64 - 65.61.137.127

  3. What is the company they use to store their infrastructure:
    - Rackspace Backbone Engineering

  4. What is the IP address of the DNS server:
    - 65.61.137.117

#### Step 3: Shodan

- What open ports and running services did Shodan find:
  - Open Ports: 80, 443, 8080
  - Services: Apache Tomcat/Coyote JSP Engine (version 1.1)

#### Step 4: Recon-ng

- Install the Recon module `xssed`. 
- Set the source to `demo.testfire.net`. 
- Run the module. 

Is Altoro Mutual vulnerable to XSS: 
  - Yes.
  ![Alt text](https://github.com/katgoods/week16/blob/master/xssshot.png "XSS Vulnerability Proof")
  
  

### Step 5: Zenmap

Your client has asked that you help identify any vulnerabilities with their file-sharing server. Using the Metasploitable machine to act as your client's server, complete the following:

- Command for Zenmap to run a service scan against the Metasploitable machine: 
  - nmap -T4 -A -v192.168.0.10
 
- Bonus command to output results into a new text file named `zenmapscan.txt`:

- Zenmap vulnerability script command: 
  - nmap --script samba-vuln-cve-2012-1182 192.168.0.10

- Once you have identified this vulnerability, answer the following questions for your client:
  1. What is the vulnerability:
    - SMB 3 (Samba)
    
  2. Why is it dangerous:
    - It allows the attacker to upload a shared library and have the server load and execute it. Complete impacts to the CIA triad (system files being shared, loss of system protection, totall shudown of affected source).

  3. What mitigation strategies can you recommendations for the client to protect their server:
    - Block port 445

---
© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
