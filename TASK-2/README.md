 Task 2: Cloud Monitoring & Alerts using AWS CloudWatch

 EC2 Instance
- AMI: Amazon Linux 2023 (x86)
- Instance Type: t3.micro (Free Tier)
- Key Pair: cloudwatch-key.pem
- Security Group: SSH allowed (0.0.0.0/0)

 Steps Performed
1. Launched EC2 instance
2. Connected via SSH using Public IP
3. Installed stress tool and generated CPU load
4. Created CloudWatch CPU Utilization Alarm (>70%)
5. Configured SNS Topic and Email alerts
6. Verified email alert received
7. Created CloudWatch Dashboard with CPU, Network In, and Disk metrics

 Screenshots
![EC2 Instance Running](https://github.com/kumbharshruti/CloudComputing-Codtech-21/blob/8e1d1c5f26fd595bc7665ba257ee4841aa5ae931/TASK-2/EC2%20Instances.png)
![CPU Alarm Created](./screenshots/cpu_alarm.png)
![SNS Email Alert](./screenshots/email_alert.png)
![CloudWatch Dashboard](./screenshots/dashboard.png)
