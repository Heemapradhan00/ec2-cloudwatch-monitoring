# ec2-cloudwatch-monitoring
## Description

This repository contains steps and configurations for setting up and monitoring AWS EC2 instances using Amazon CloudWatch. It includes the process for launching EC2 instances, configuring target groups, and setting up alarms for performance monitoring.


### Step 1: Launch EC2 Instances
1. **Instance for `/api`**  
   - Launch an EC2 instance via the AWS Management Console.
   - Use Amazon Linux 2 or Ubuntu as the AMI.
   - Configure HTTP (port 80) access in the Security Group.
   - Ensure the instance is in the same VPC and subnet as other resources.

2. **Instance for `/app`**  
   - Launch a second EC2 instance following the same steps, configured for the `/app` path.



### Step 2: Configure Target Groups
- Set up target groups to route traffic for `/api` and `/app` paths effectively using an Application Load Balancer (ALB).



### Step 3: Create a CloudWatch Alarm
1. Navigate to **Amazon CloudWatch** in the AWS console.
2. Under **Alarms**, create a new alarm to monitor **CPU Utilization**.
3. Select the EC2 instance metric for **CPU Utilization**.
4. Configure the alarm with the following parameters:  
   - **Statistic:** Average  
   - **Period:** 1 minute  
   - **Threshold:** Greater than 80%  
   - **Evaluation Periods:** 5 (alarm triggers after CPU exceeds 80% for 5 consecutive minutes).

5. Set up an **SNS Topic** for notifications.
6. Confirm the subscription and finalize the alarm creation.


## Objective
- Launch and configure EC2 instances.
- Set up and utilize an Application Load Balancer (ALB).
- Monitor performance using CloudWatch alarms.
- Ensure effective cloud resource management and performance monitoring.

![image](https://github.com/user-attachments/assets/2caa5c60-05f5-48ca-9826-7f8cf9882385)
