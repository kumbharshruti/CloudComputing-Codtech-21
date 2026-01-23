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
![CPU Alarm Created](https://github.com/kumbharshruti/CloudComputing-Codtech-21/blob/56368367b0f66585fb3c40f6e90562b104b519b9/TASK-2/Alarms.png)
![SNS Email Alert](https://github.com/kumbharshruti/CloudComputing-Codtech-21/blob/c76c29af184d85b8f91d8833c19a8cdb4c9f34e8/TASK-2/sms%20email%20alarm.jpeg)
![CloudWatch Dashboard](./screenshots/dashboard.png)
