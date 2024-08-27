
![Screenshot 2024-08-26 at 9 17 10 PM](https://github.com/user-attachments/assets/702e0914-70bb-46e1-8ef5-30402f27c1d2)

# 🛡️ Network Security Challenge: Mastering Nmap, Telnet, and Hydra 🛡️

Welcome to my **Network Security Challenge** project! This challenge serves as the ultimate test of the skills and techniques I've honed in the **Network Security Module** on TryHackMe. Armed with powerful tools likee Nmap, Telnet, and Hydra, I have dived deep into the art of vulnerability scanning, remote access, and password cracking to secure and assess network environments. Join me on this journey where I break down the steps and strategies used to conquer each task, showcasing my mastery in network defense and offensive security!

## **Challenge Questions**
- Quick note: All questions will be answered using Nmap, Telnet, and Hydra 😃

  **1.)** What is the highest port number being open less than 10,000? ***8080***
  
  **2.)** There is an open port outside the common 1000 ports; it is above 10,000. What is it? ***10021***
  
  **3.)** How many TCP ports are open? ***6***
  
![NetSec(1)](https://github.com/user-attachments/assets/00af5b58-a2dc-4ed5-878d-fd6e054d4250)


- Let's dive into the answers:
  - To begin, I ran a simple nmap scan: **nmap -sC -sV -p- -T4 --min-rate=9326 -vv 10.10.82.134. Lets break down the script:
    - **-sC**: Runs specific scripts on the target (**10.10.82.134**) to see what actions or vulnerabilities may exist.
    - **-sV**: Detects the versions of services running on a target.
    - **-p-**: Scans all available ports.
    - **-T4**: Speeds up the scan (T5 is the fastest).
    - **--min-rate=9326**: Nmap sends packets at a rate of 9326 per second.
    - **-vv**: Produces a very verbose output, providing more detailed information during the scan.

 **4.)** What is the flag hidden in HTTP server header? ***THM{web_server_25352}***
 
 **5.)** What is the flag hidden in the SSH server header? ***THM{946219583339}***

**6.)** We have an FTP server listening on a nonstandard port. What is the version of the FTP server? ***vsftpd 3.0.3***

- Answer breakdown:
  - Scroll down slightly from the previous screenshot to capture the needed flags 😃
  - We are also able to discover the FTP server version listening.

![NetSec(2)](https://github.com/user-attachments/assets/fc5a9031-e795-400a-a972-630de3c69198)

 
 **7.)** We learned two usernames using social engineering: **eddie** and **quinn**. What is the flag hidden in one of these two account files and accessible via 
         FTP? ***THM{321452667098}***
         
- Answer breakdown:
   - Run **hydra** to brute-force the password for usernames.
     - Scripts ran: **hydra -l [username] -P /usr/share/wordlists/rockyou.txt -vV [TARGET_MACHINE_IP] [port number]
     - ***Note***: The **/usr/share/wordlists/rockyou.txt** file is a pre-complied list of breached passwords.

![NetSec(eddie)](https://github.com/user-attachments/assets/95c8a649-e860-4d3e-9c71-ec9af659720c)

![NetSec(quinn)](https://github.com/user-attachments/assets/6611e4a5-93aa-4d8a-a8b0-518bdf9e016e)

- Next, we must login to the ftp server and discover our flag 😃

         
 **8.)** Browsing **http://10.10.82.134:8080** displays a small challenge that will give you a flag once you solve it. What is the flag? ***THM{f7443f99}***

 - Answer breakdown:
   - To finish our challenge we navigate to the above domain: **nmap -sN [TARGET_MACHINE_IP]**
   - **Nmap -sN** is used to perform a TCP Null Scan; we can probe the target system by sending packets without any flags set in the TCP header, with the goal to 
     determine the state of ports on the target.

## Conclusion 

In this module, we had a blast diving into network security with tools like Nmap, telnet, and hydra. From mastering basic port scans to uncovering vulnerabilities through social engineering, every step felt like a thrilling puzzle. Along the way, I learned the ins and outs of TCP and UDP port scanning, explored different Nmap flags, and cracked some fun challenges using FTP and SSH. Though some tasks test my skills and patience, it was never too difficult - just the right balance of challenge and learning. This journey helped solidify my understanding of network security, and I can't wait for what is next!
