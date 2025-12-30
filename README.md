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



**✅ Task 2: User Management and Access Control**
===============================================

Secure user accounts were created for the new developers with isolated workspaces and enforced security policies.
👤 Users Created
sarah
mike
📁 Workspace Directories
Sarah: /home/sarah/workspace
Mike: /home/mike/workspace
🔐 Security Controls Implemented
Directory permissions set to 700
Ownership restricted to respective users
Password expiration enforced every 30 days
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
📁 Repository Contents
Monitoring scripts and logs
User management configurations
Backup scripts and cron jobs
Verification logs
Documentation and screenshots
All scripts, logs, and documentation related to the assignment are available in this repository.
🏁 Conclusion
This project demonstrates the implementation of core DevOps responsibilities, including:
System monitoring and logging
Secure user and access management
Automated, scheduled, and verified backups
Security-focused configuration practices
The setup follows industry-standard DevOps practices and is suitable for real-world development environments.
