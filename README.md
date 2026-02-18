🔐 Log Analysis using SIEM (Splunk Enterprise)
📌 Project Overview

This project demonstrates hands-on Security Information and Event Management (SIEM) log analysis using Splunk Enterprise in a simulated SOC environment.

The objective was to ingest, analyze, and correlate logs from multiple systems to detect malicious activity such as:

Brute-force attacks

Privilege escalation

Persistence mechanisms

Suspicious process execution

Web application attacks

🛠️ Tools & Technologies

Splunk Enterprise

Windows Event Logs

Sysmon

Linux Authentication Logs (auth.log)

Web Server Access Logs

SPL (Search Processing Language)

🖥️ Log Sources Analyzed
1️⃣ Windows Logs

Windows Event Logs

Sysmon logs

2️⃣ Linux Logs

Authentication logs

System logs

3️⃣ Web Application Logs

WordPress access logs

HTTP request logs

🚨 Investigation Findings
🔍 Windows Log Analysis

Detected:

Suspicious process execution (SharePoInt.exe)

Abnormal outbound network connection

Persistence via scheduled task ("Office365 Install")

Malicious file hash identified

Indicators Identified:

External IP: 10.10.114.80

MD5 Hash: 770D14FFA142F09730B415506249E7D1

🔍 Linux Log Analysis

Detected:

Multiple failed SSH login attempts

Successful brute-force login

Privilege escalation to root

Creation of new SSH user

Persistence via cron job

Indicators Identified:

Source IP: 10.14.94.82

Privileged User: jack-brown

Persistence Port: 7654

🔍 Web Application Log Analysis

Detected:

High-volume POST requests targeting /wp-login.php

Repeated authentication attempts

Automated attack using WPScan

Indicators Identified:

Source IP: 10.10.243.134

Attack Type: Brute-force

🔗 Key SIEM Concepts Applied

Log Centralization

Event Correlation

Normalization

Indicator of Compromise (IOC) Identification

Attack Timeline Reconstruction

📊 Sample SPL Queries Used
# Detect failed SSH logins
index=linux "Failed password"

# Detect suspicious Windows process
index=windows Image="*SharePoInt.exe*"

# Detect high-volume POST requests
index=web method=POST uri="/wp-login.php"

🎯 Skills Demonstrated

SIEM-based threat detection

Log correlation across multiple sources

Brute-force attack detection

Privilege escalation identification

Persistence mechanism detection

SOC-style incident investigation

📈 Learning Outcome

This project strengthened practical SOC skills by simulating real-world attack detection using Splunk Enterprise. It demonstrates the ability to analyze logs, identify malicious activity, and extract actionable security insights.

🚀 Future Improvements

MITRE ATT&CK mapping

Alert rule creation

Dashboard development

Severity classification of incidents
