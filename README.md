# Testing-Linux-and-Servers_hero
Assigmnet-3-Testing-Linux-and-Servers
DevOps Environment Setup & Management Assignment
Overview
This repository contains the implementation for setting up and managing a secure, monitored, and well-maintained development environment as part of a DevOps assignment.

The objective of this project is to assist a Senior DevOps Engineer in:

Monitoring system performance
Managing user access securely
Automating and verifying backups for web servers
The environment is configured for two developers:

Sarah – Apache Web Server
Mike – Nginx Web Server
Tasks Implemented
Task 1: System Monitoring Setup
Configured system monitoring tools to ensure visibility into system health and performance.

Tools & Commands Used:

htop / nmon for CPU, memory, and process monitoring
df -h for disk usage
du -sh for directory-level storage analysis
ps for identifying resource-intensive processes
Logging:

System metrics are logged in:
image image
/var/log/system_monitoring/metrics.log

Task 2: User Management and Access Control
Created secure user accounts with isolated workspaces and enforced password policies.

Users Created:

sarah
mike
Workspace Directories:

Sarah: /home/sarah/workspace
Mike: /home/mike/workspace
Security Controls:

Directory permissions set to 700
Ownership restricted to respective users
Password expiration enforced every 30 days
Password warning enabled before expiry
image image image
Task 3: Backup Configuration for Web Servers
Automated backups for Apache and Nginx servers with scheduled cron jobs and integrity verification.

Apache Backup (Sarah)
Configuration: /etc/httpd/
Document Root: /var/www/html/
Script: apache_backup.sh
Nginx Backup (Mike)
Configuration: /etc/nginx/
Document Root: /usr/share/nginx/html/
Script: nginx_backup.sh
Backup Schedule:

Every Tuesday at 12:00 AM
Managed via cron
Backup Location: image

Cron Job Configuration $ sudo crontab -l 0 0 * * 2 /usr/local/bin/apache_backup.sh 0 0 * * 2 /usr/local/bin/nginx_backup.sh

All scripts, logs, and documentation are available in this repository.
