
<p align="center">
<img src="https://media2.giphy.com/media/v1.Y2lkPWVjZjA1ZTQ3OTA4YmJ2NnYwZjkweWQzemExcmJtbWZoZTFxcWU2Yzh3NXpjYW15dSZlcD12MV9naWZzX3JlbGF0ZWQmY3Q9Zw/qy1VAsXjWNR6ZD6HBG/giphy.webp", width="300", height="300">
</p>

<h1 align="center">ZER0CAL</h1>
<h4 align="center"> ZER0CAL - linux-based backdoor builder</h4>

### DESCRIPTION
ZER0CAL is a Linux-based backdoor designed for ethical penetration testing and cybersecurity research. It uses Google Calendar as a stealthy Command and Control (C2) server to handle backdoors on Linux systems, allowing for remote command execution through event-based communication. The tool injects a polymorphic dropper into regular Python code, ensuring each version is unique by modifying variables, functions, and signatures to evade detection and stay under the radar. This adaptive approach means every build features fresh code changes, making it harder for security tools to identify patterns. Inspired by APT41 techniques and evasion strategies, ZER0CAL provides a robust framework for exploring advanced C2 methodologies in controlled, ethical settings.

### Features:
  * Polymorphic Injection: Automatically modifies code (e.g., variables and functions) in each build to create unique signatures, making it harder for antivirus tools to detect.
  
  * Google Calendar C2: Uses Google Calendar events as a covert channel for backdoor communication, allowing remote command execution on Linux targets.
  
  * Dropper Builder: Injects a custom dropper into any legitimate Python script, transforming it into a backdoor payload.
  
  * Linux Backdoor Deployment: Focuses on Linux systems, with features for persistent execution and event-based polling.

### SETUP
Setup (Google Calendar C2)

Follow the steps below to configure your Google Cloud project and enable Google Calendar API for C2 communication.

1. Create a Google Cloud Project and Service Account

    Go to: https://console.cloud.google.com

    From the sidebar, go to IAM & Admin → Service Accounts

    Click + Create Project
     * Project name: (e.g.,) rat-calendar-c2
     * Click Create

    Click + Create Service Account
     * Service account name: e.g. test-c2
     * Description: (optional)
     * Click Create and Continue

    Grant this service account access:
      * Role: Owner
      * Click Continue → Done

    Click your newly created service account
      * Go to the Keys tab
      * Click Add Key → Create New Key
      * Select JSON, then click Create
      * Save the file as: creds.json in your directory

3. Share Google Calendar with Service Account

    Visit: https://calendar.google.com

    On the left, click the 3-dot menu beside your calendar → Settings and sharing

    Scroll to Share with specific people
     * Click + Add people and groups
     * Paste your Service Account email
     * Example: test-c2@your-project-id.iam.gserviceaccount.com
     * Set permission to: Make changes and manage sharing
     * Click Send

5. Enable Google Calendar API

     * Go to: https://console.cloud.google.com/apis/library
     * Search for: Google Calendar API
     * Click it → Click Enable

    
### INSTALLATION
    git clone https://github.com/0xbitx/DEDSEC_ZER0CAL.git
    cd DEDSEC_ZER0CAL
    chmod +x dedsec-zer0cal
    sudo ./dedsec-zer0cal
    

### TESTED ON FOLLOWING
* Kali Linux 
* Parrot OS 
  
## Legal Disclaimer

This tool is intended for educational and security research purposes only. Unauthorized usage may be illegal in your jurisdiction. The author is not responsible for any misuse of this tool.
