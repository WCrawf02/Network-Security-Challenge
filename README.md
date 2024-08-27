
![Screenshot 2024-08-26 at 9 17 10 PM](https://github.com/user-attachments/assets/702e0914-70bb-46e1-8ef5-30402f27c1d2)

# 🛡️ Network Security Challenge: Mastering Nmap, Telnet, and Hydra 🛡️

Welcome to my **Network Security Challenge** project! This challenge serves as the ultimate test of the skills and techniques I've honed in the **Network Security Module** on TryHackMe. Armed with powerful tools likee Nmap, Telnet, and Hydra, I have dived deep into the art of vulnerability scanning, remote access, and password cracking to secure and assess network environments. Join me on this journey where I break down the steps and strategies used to conquer each task, showcasing my mastery in network defense and offensive security!

## **Challenge Questions**
- Quick note: All questions will be answered using Nmap, Telnet, and Hydra 😃

  **1.)** What is the highest port number being open less than 10,000? ***8080***
  
  **2.)** There is an open port outside the common 1000 ports; it is above 10,000. What is it? ***10021***
  
  **3.)** How many TCP ports are open? ***6***
  

![NetSec(1)](https://github.com/user-attachments/assets/5a8a443f-13c4-4715-98ec-fb257aaf958c)

- Let's dive into the answers:
  - To begin, I ran a simple nmap scan: **nmap -sC -sV -p- -T4 --min-rate=9326 -vv 10.10.82.134. Lets break down the script:
    - **-sC**: Runs specific scripts on the target (**10.10.82.134**) to see what actions or vulnerabilities may exist.
    - **-sV**: Detects the versions of services running on a target.
    - **-p-**: Scans all available ports.
    - **-T4**: Speeds up the scan (T5 is the fastest).
    - **--min-rate=9326**: Nmap sends packets at a rate of 9326 per second.
    - **-vv**: Produces a very verbose output, providing more detailed information during the scan.


