#  Email_Notification

As a **Cloud Engineer**, I built a **serverless event-driven email notification system** using **AWS S3, SNS, Lambda, IAM, and CloudWatch**.  
This system automatically sends an email notification whenever a new file is uploaded to an S3 bucket.

---

##  Architecture

The overall project architecture is shown below:

![Architecture Diagram](image-1.png)

---

##  Workflow

### 1. File Upload to S3
A file is uploaded to an **S3 bucket**, which triggers the workflow.

![S3 Bucket](image-2.png)

---

### 2. SNS Notification
The S3 event is configured to publish to an **Amazon SNS Topic**, which handles the delivery of notifications.

![SNS](image-3.png)

---

### 3. IAM Role & Permissions
A dedicated **IAM Role** was created for the Lambda function with the following managed policies:
- `AmazonS3FullAccess`
- `AmazonSNSFullAccess`
- `AWSLambda_FullAccess`
- `AWSLambdaBasicExecutionRole`

![IAM Policy](image-4.png)

---

### 4. Lambda Function Execution
The **Lambda function** is triggered when a new file is uploaded.  
It processes the event and sends details to the SNS topic.

![Lambda Function](image-5.png)

---

### 5. Email Notification
The subscribed email address receives structured alerts with file details (name, size, timestamp, bucket).

![Email Output](output.png)

---

### 6. Monitoring with CloudWatch
Logs and metrics from Lambda execution are monitored in **CloudWatch** for debugging and tracking performance.

---

## 📂 Resources Created
- **S3 Bucket:** `emailnotification01`
- **SNS Topic:** `notification-01`
- **Lambda Function:** `notification-01`
- **IAM Role:** `notification`

---

##  Sample Email Notification


### final output ![output](image.png)

