\# RTS-1087 – Linux Permission Denied Issue (Day 3)



\*\*Engineer:\*\* Sompassate Donatien Ernest Yameogo  

\*\*Role:\*\* Cloud / DevOps Engineer  

\*\*Company:\*\* Radiant  

\*\*Environment:\*\* AWS EC2 (Amazon Linux 2)  

\*\*Severity:\*\* Medium  

\*\*Status:\*\* Completed  



---



\## 1. Issue Summary

The application directory `/opt/app` returned \*\*Permission denied\*\* errors, preventing normal access and execution on the EC2 instance.



---



\## 2. Impact

\- Application access was blocked

\- Risk of service disruption

\- Required immediate remediation



---



\## 3. Investigation Steps

\- Reviewed directory permissions using `ls -l`

\- Verified ownership of `/opt/app`

\- Checked running processes

\- Confirmed SSH daemon health

\- Reviewed system logs for errors



---



\## 4. Resolution

Corrected ownership and permissions on the application directory and verified system services.



```bash

sudo chown -R ec2-user:ec2-user /opt/app

sudo chmod -R 755 /opt/app

systemctl status sshd

journalctl -u sshd --no-pager -n 20



