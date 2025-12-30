# Testing-Linux-and-Servers_hero
Assigmnet-3-Testing-Linux-and-Servers

DevOps Environment Setup & Management Assignment:-
==================================================
📌 **Overview**
--------------
This repository contains the implementation of a secure, monitored, and well-maintained DevOps development environment, created as part of an academic DevOps assignment.
The objective of this project is to assist a Senior DevOps Engineer (Rahul) in setting up an environment that ensures:
>> Continuous system monitoring
>> Secure user management and access control
>> Automated and verified backups for web servers

*The environment is configured for two developers:*

Sarah – Responsible for an Apache Web Server
Mike – Responsible for an Nginx Web Server
All tasks were implemented on a Linux-based (Ubuntu/Amazon Linux) EC2 environment following DevOps best practices.

Here  i am using **AWS-EC2 engine** for implementing all scenarios for user creation and backup scripts with cronjobs.

**✅ Task 1: System Monitoring Setup**
==================================
System monitoring tools were installed and configured to provide visibility into CPU usage, memory consumption, disk utilization, and running processes.
🔧 Tools & Commands Used
htop / nmon – Real-time CPU, memory, and process monitoring
df -h – Disk space usage monitoring
du -sh – Directory-level disk usage analysis
ps – Identification of resource-intensive processes
📊 Logging & Reporting
System metrics are automatically logged for review and troubleshooting.
Log file location:
/var/log/system_monitoring/metrics.log
These logs help with performance analysis, troubleshooting, and capacity planning.

<img width="940" height="197" alt="image" src="https://github.com/user-attachments/assets/f7e2b147-9b54-4fa2-b33d-32e2d0869ec5" />

<img width="940" height="390" alt="image" src="https://github.com/user-attachments/assets/f4245212-5e1a-450d-bf89-c4ece39b58fa" />

<img width="940" height="162" alt="image" src="https://github.com/user-attachments/assets/8036f164-946e-4f89-a939-927fc7bf63b0" />

<img width="940" height="206" alt="image" src="https://github.com/user-attachments/assets/60c6272a-093b-40e1-8ae6-e8e7ea051a2d" />

<img width="940" height="213" alt="image" src="https://github.com/user-attachments/assets/42bfcb63-b3e8-4609-a2fa-66b44d046049" />

<img width="940" height="209" alt="image" src="https://github.com/user-attachments/assets/146e50a9-1a82-40b2-b1b6-0bf3af759db8" />

<img width="479" height="316" alt="image" src="https://github.com/user-attachments/assets/540c7fa0-6692-4701-8af9-15788874eaac" />

<img width="940" height="284" alt="image" src="https://github.com/user-attachments/assets/2e48f6e2-003d-4410-a350-b3e74f4f2734" />


**✅ Task 2: User Management and Access Control**
===============================================

Secure user accounts were created for the new developers with isolated workspaces and enforced security policies.
👤 Users Created
sarah
mike

<img width="940" height="468" alt="image" src="https://github.com/user-attachments/assets/fc61fb8b-1154-4dee-8a0f-091578be8b62" />

📁 Workspace Directories
Sarah: /home/sarah/workspace
Mike: /home/mike/workspace
<img width="940" height="456" alt="image" src="https://github.com/user-attachments/assets/198b143c-eee9-4d75-a401-965e28218838" />

🔐 Security Controls Implemented
Directory permissions set to 700
Ownership restricted to respective users
Password expiration enforced every 30 days
<img width="940" height="349" alt="image" src="https://github.com/user-attachments/assets/f9c189a6-9cba-4013-9a91-2ecc70beadb7" />

Password expiry warnings enabled prior to expiration
These measures ensure data confidentiality, access isolation, and compliance with security standards.

**✅ Task 3: Automated Backup Configuration for Web Servers**:-
==============================================================

Automated backup solutions were implemented for both Apache and Nginx servers to ensure data integrity and disaster recovery readiness.
🌐 Apache Backup (Sarah)
Configuration Directory: /etc/httpd/ (or /etc/apache2/)
Document Root: /var/www/html/
Backup Script: apache_backup.sh
🌐 Nginx Backup (Mike)
Configuration Directory: /etc/nginx/
Document Root: /usr/share/nginx/html/
Backup Script: nginx_backup.sh

<img width="940" height="456" alt="image" src="https://github.com/user-attachments/assets/d9ae4343-67cb-4e1a-8f9a-22efc680ac29" />

⏰ Backup Schedule
Frequency: Every Tuesday
Time: 12:00 AM
Scheduler: cron
📂 Backup Storage Location
/backups/
🗂 Naming Convention
apache_backup_YYYY-MM-DD.tar.gz
nginx_backup_YYYY-MM-DD.tar.gz
🔍 Backup Integrity Verification
After each backup execution, the contents of the compressed archive are verified and logged.
📋 Cron Job Configuration
sudo crontab -l
0 0 * * 2 /usr/local/bin/apache_backup.sh
0 0 * * 2 /usr/local/bin/nginx_backup.sh
Verification logs confirm that backups are successfully created and readable.

<img width="891" height="179" alt="image" src="https://github.com/user-attachments/assets/89dd20cc-0f9b-41b4-b56f-5b5db23480df" />


**🏁 Conclusion**
===========================
This project demonstrates the implementation of core DevOps responsibilities, including:
System monitoring and logging
Secure user and access management
Automated, scheduled, and verified backups
Security-focused configuration practices
The setup follows industry-standard DevOps practices and is suitable for real-world development environments.
