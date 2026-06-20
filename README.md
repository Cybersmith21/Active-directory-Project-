# Active-directory-Project-
## Objective
* I built a complete Active Directory home lab with four virtual machines to learn how real corporate networks work and how to detect attacks against them. The lab includes a Windows Server acting as a Domain Controller, an Ubuntu server running Splunk as my SIEM, a Windows 10 target machine, and Kali Linux as my attack platform. By setting up centralized logging with Splunk and generating real attack telemetry, I got hands-on experience detecting brute-force attempts, privilege escalations, and other malicious activities that security analysts face daily. Within this controlled environment, I was able to simulate attacks, capture the logs, and actually see what suspicious activity looks like from a defender's perspective.

## Skills Learned
* Setting up a full Active Directory domain from scratch, including promoting a server to a Domain Controller and configuring DNS
* Installing and configuring Splunk Enterprise on Linux to serve as a centralized SIEM for log aggregation and analysis
* Deploying Splunk Universal Forwarders on Windows machines to forward telemetry to the Splunk server
* Installing and configuring Sysmon with custom configurations for detailed endpoint monitoring
* Creating Organizational Units (OUs) and managing users in Active Directory
* Joining Windows machines to a domain and troubleshooting domain resolution issues
* Using Kali Linux tools like Crowbar to simulate real-world brute-force attacks
* Executing Atomic Red Team tests mapped to the MITRE ATT&CK framework to generate realistic attack telemetry
* Searching and correlating security events in Splunk to identify attack patterns like failed logon attempts (Event 4625) and successful logons (Event 4624)

## Tools Used 
* VirtualBox – My hypervisor of choice for running all four VMs on a single machine
* Windows Server 2019/2022 – The backbone of my Active Directory environment, acting as the Domain Controller for mydfir.local
* Ubuntu Server – Hosting my Splunk Enterprise instance to collect and analyze all the logs
* Windows 10 – My target machine joined to the domain, running Splunk Forwarder and Sysmon
* Kali Linux – My attacker machine for launching brute-force attacks and testing detection capabilities
* Splunk Enterprise – The SIEM platform where all the magic happens, ingesting logs and letting me search for threats
* Splunk Universal Forwarder – Lightweight agent installed on Windows machines to push logs to the Splunk server
* Sysmon – Powerful system monitor from Microsoft Sysinternals that gives deep visibility into endpoint activity
* Crowbar – Bruteforce tool on Kali that I used to test the target machine's defenses
* Atomic Red Team – Library of attack simulations mapped to MITRE ATT&CK for realistic threat testing

## Screenshots/Lab In Action 
* Network Diagram : My full lab layout showing all four VMs on the 192.168.10.0/24 NAT network with their assigned static IP addresses
  
* Domain Join : Windows 10 successfully joined to MYDFIR.LOCAL, now part of the Active Directory domain
* Crowbar Attack in Progress : Kali Linux executing a password brute-force attack against the Windows 10 machine
* Splunk Detection : Searching Splunk and finding Event 4625 (failed logins) and 4624 (successful login) patterns showing the attack was caught
* Atomic Red Team Execution : Running the T1136.001 test to create a local user and seeing it detected in Splunk
* PowerShell Attack Detection : Running T1059.001 and correlating the PowerShell logs in Splunk

## Security & Compliance
* Caution: This lab is strictly for educational use in an isolated virtual environment. Do not replicate this setup on production networks. The Atomic Red Team tests and brute-force attacks are real threat simulations; only run them against systems you own or have explicit permission to test.
* Compliance: Ensure all testing complies with local laws and organizational policies. Never use these techniques against unauthorized systems.

## Why This Lab Matters 
* This project completely changed how I understand corporate security. Before building this, I knew attacks existed but had never seen what they actually look like in logs. Setting up the entire environment myself, from configuring Active Directory to launching brute-force attacks, gave me a much deeper appreciation for what defenders deal with daily. The most eye-opening moment was watching the Splunk dashboard light up during the Crowbar attack and seeing the failed logon events flood in. It made me realize how crucial SIEM visibility is for catching attacks in progress.

## What I'd Do Next
* Experiment with more Atomic Red Team techniques covering different MITRE tactics like Persistence and Privilege Escalation
* Extend the lab by adding more target machines and realistic user activity

## Credits and inspiration
* this project was mapped very well and made easy to really understand what I was doing by the youtuber MYDFIR. If you feel nervous about starting something like this I would 100% recommend his channel.
* https://www.youtube.com/watch?v=VnvgfQEv7Jo 
