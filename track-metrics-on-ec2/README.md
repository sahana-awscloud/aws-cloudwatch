AWS EC2 CPU Utilization Monitoring Project

This project demonstrates how to monitor CPU utilization of an AWS EC2 instance using Amazon CloudWatch Alarms. A Python script is used to artificially spike CPU usage, and a CloudWatch alarm is configured to send an email notification when CPU utilization crosses 80%.

Project Overview

1. Launch an EC2 instance.
2. Write and execute a Python script to create CPU load.
3. Configure a CloudWatch Alarm that triggers when CPU usage exceeds 80%.
4. Connect the alarm to an SNS topic for email notifications.
5. Verify by running the script and monitoring the alarm status.

Prerequisites

1. AWS Account with access to EC2, CloudWatch, SNS
2. EC2 instance running Ubuntu
3. python installed on EC2

Configuring the CloudWatch Alarm

1. Open CloudWatch Console → Alarms → Create Alarm
2. Select EC2 Instance Metrics → CPUUtilization
3. Set threshold:
      Condition: Greater than 80%
      Period: 1 Minute
4. Create an SNS topic and subscribe your email address
5. Attach the SNS topic to the alarm

Testing the Setup

1. Start the cpu_spike.py script
2. Monitor CPU in CloudWatch → Metrics → EC2 → CPUUtilization
3. When CPU > 80%, the alarm changes to ALARM state
4. You will receive an email notification

Deliverables

EC2 instance with script
CloudWatch Alarm configured at 80% threshold
Email notification received when CPU threshold is breached
