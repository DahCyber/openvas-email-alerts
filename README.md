# openvas-email-alerts
Cybersecurity project: Sending OpenVAS scan results via secure Gmail SMTP.
# OpenVAS Email Alert Integration with Gmail

## Overview
This project demonstrates how I configured OpenVAS (inside a Docker container) to send automated vulnerability scan alerts via Gmail SMTP. This setup enhances alerting and response capabilities by providing email notifications when scans are completed or new vulnerabilities are detected.

## Technologies Used
- OpenVAS (Greenbone Vulnerability Manager)
- Docker
- msmtp (lightweight SMTP client)
- Gmail SMTP Server
- TLS/SSL Encryption

## Objectives
- Automate OpenVAS alert notifications.
- Use secure email delivery with Gmail App Passwords.
- Integrate email into vulnerability management workflows.

## Setup Guide

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/openvas-email-alerts.git
cd openvas-email-alerts

Run Docker OpenVAS
This project uses Docker Compose to run OpenVAS.

bash

docker compose up -d

The container exposes the Greenbone web interface at http://localhost:9392. Default credentials:

Username: admin

Password: admin123 (change in docker-compose.yml!)

3. Configure msmtp for Gmail Alerts
This project includes a sample email configuration: msmtprc.example

Copy the example file and rename it:

bash
Copy code
cp msmtprc.example ~/.msmtprc
chmod 600 ~/.msmtprc
Edit it and replace:

your-email@gmail.com with your real Gmail address

your-app-password with a Gmail App Password

Test email from terminal:

bash

echo "Test alert from OpenVAS setup." | msmtp recipient@example.com


5. Results
OpenVAS now sends vulnerability scan alerts directly to your inbox.

Improved visibility and real-time awareness of scan activity.



