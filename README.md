# 🖥️ EC2 Instance Monitoring with CloudWatch

This project demonstrates how to monitor an Amazon EC2 instance using AWS CloudWatch, set up a custom alarm based on CPU utilization, and receive email notifications when thresholds are breached.

---

## 🚀 Project Overview

As part of cloud infrastructure monitoring, I configured an EC2 instance with the CloudWatch agent, created a CPU-based alarm, and tested it by artificially increasing CPU usage. This project showcases real-time monitoring and alerting using native AWS tools.

---

## 🛠️ Technologies Used

- **Amazon EC2**
- **AWS IAM**
- **Amazon CloudWatch**
- **CloudWatch Agent**
- **Linux Terminal / SSH**
- **SNS (Simple Notification Service)**

---

## 📌 Key Features

- Launched and configured a **t2.micro EC2 instance** on Amazon Linux/Ubuntu
- Created and attached an **IAM Role** to allow CloudWatch agent permissions
- Installed and started the **CloudWatch Agent** to send metrics
- Set up a **CloudWatch Alarm** to monitor CPU utilization
- Triggered alarm using `stress` command to simulate high CPU load
- Received **email notification** when alarm transitioned to ALARM state

---

## 📈 Alarm Configuration

| Parameter              | Value                          |
|------------------------|---------------------------------|
| Metric                 | `CPUUtilization`               |
| Threshold              | `>= 30%`                       |
| Evaluation Period      | `1 x 5-minute datapoint`       |
| Notification Method    | Email via **SNS topic**        |
| Region                 | `us-east-1 (N. Virginia)`      |

---

## 📬 Email Alert Screenshot

>![email-alert png](https://github.com/user-attachments/assets/9262cd84-158f-466c-ac93-30260b1828ce)


---

## 📊 Metric Graph Screenshot

> ![cpu-metric png](https://github.com/user-attachments/assets/7e3860d7-edbf-4b50-9a78-25b7f1d7d56c)


---

## 🔁 Steps to Reproduce

1. **Launch EC2 Instance**
   - Choose Amazon Linux 2 or Ubuntu
   - t2.micro (Free Tier)
   - Attach IAM role with `CloudWatchAgentServerPolicy`

2. **Install CloudWatch Agent**

   ```bash
   sudo yum install amazon-cloudwatch-agent -y
