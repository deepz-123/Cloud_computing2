# Cloud_computing2
**COMPANY**      : CODTECH IT SOLUTIONS
**NAME**         : DEEPAK 
**INTERN ID**    : CT04MRV
**DOMAIN**       : CLOUD COMPUTING 
**DURATION **    : 4 MONTHS 
**MENTOR**       : NEELA SANTOSH 
**DESCRIPTION**  :
**
Cloud Monitoring and Alerts Using AWS CloudWatch**

This project demonstrates how to set up monitoring and alerting for a cloud-based application running on AWS using Amazon CloudWatch. The focus is on configuring metrics and alarms that enable real-time observability, proactive incident response, and infrastructure health monitoring.

**Tools & Services Used**

AWS EC2 – to run the cloud application

Amazon CloudWatch – for monitoring and alerting

Amazon SNS – to send email notifications on alarm triggers

**Step-by-Step Setup**

🔹 1. Launch the Cloud Application

1. Go to EC2 from the AWS Console.


2. Launch an EC2 instance with Amazon Linux 2.


3. Configure security group to allow:

SSH (port 22) for remote access

HTTP (port 80) for web app monitoring



4. Deploy a sample app or web server (e.g., Apache/NGINX).


5. Confirm the instance is running and accessible via public IP.




---

🔹 2. Enable CloudWatch Monitoring

1. Select your EC2 instance.


2. Click on Actions > Monitor and troubleshoot > Manage CloudWatch monitoring.


3. Enable Detailed Monitoring for 1-minute metric granularity (optional but recommended).


4. Save settings.




---

🔹 3. Create a CloudWatch Alarm

1. Navigate to the CloudWatch service.


2. In the sidebar, click on Alarms > Create alarm.


3. Select a metric for monitoring (e.g., EC2 > Per-Instance Metrics > CPUUtilization).


4. Define alarm conditions:

Threshold: e.g., trigger alarm if CPU > 70%

Period: evaluate every 1 minute

Evaluation: 1 out of 1 data points



5. Click Next to configure actions.




---

🔹 4. Set Up Notifications with SNS

1. Create a new SNS topic if not already available.


2. Add an email subscriber (your email address) to the topic.


3. Confirm the subscription from your email inbox.


4. Link this SNS topic to your alarm to receive notifications.




---

🔹 5. Name and Finalize Alarm

1. Name your alarm something descriptive, e.g., App-HighCPU-Alarm.


2. Review and click Create alarm.




---

✅ Verifying the Alarm

1. SSH into the instance:

ssh -i your-key.pem ec2-user@your-public-ip


2. Install and run a CPU stress test to trigger the alarm:

sudo yum install stress -y
stress --cpu 2 --timeout 60


3. Wait for the alarm to change status to ALARM.


4. You should receive an email notification from the SNS topic.

**OUTPUT**
