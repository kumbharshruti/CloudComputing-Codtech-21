# Multi-Cloud Data Transfer with AWS and GCP

![](https://github.com/kumbharshruti/CloudComputing-Codtech-21/blob/d37dc6d921f95ccbc2a22c932fa036399eab53f0/TASK-3/First.png)

# Introducing Today's Project!

- In this project, I will demonstrate how to build a multi-cloud storage system by backing up data from AWS S3 to Google Cloud Storage. I'm doing this project to learn how to connect cloud platforms and automate cross-cloud data transfers.

## Tools and concepts

- Services I used were AWS IAM, GCP Storage Transfer Service, AWS S3, and GCP Cloud Storage. Key concepts I learned include cross-cloud access, setting up IAM roles, data transfer between clouds, and configuring storage buckets.

## Project reflection

- This project took me approximately 1 hour. The most challenging part was setting up the custom IAM role and trust policy. It was most rewarding to see the data successfully transfer from AWS to GCP with minimal effort.

# Multi‑Cloud Architecture Overview

## This setup illustrates a cross‑cloud workflow where resources from AWS and Google Cloud are integrated:

1. User
- The end‑user initiates requests (e.g., uploading, retrieving, or processing files).

2. AWS EC2 Instance
- Acts as the compute environment.
- Runs applications or scripts that handle file operations.
- Provides the bridge between the user and cloud storage.
  
3. File Access Layer
- Middleware logic or APIs that manage how files are read/written.
- Ensures secure authentication and data transfer between platforms.
- Could involve SDKs, REST APIs, or storage transfer services.

4. Google Cloud Storage (GCS)
- Serves as the storage backend.
- Files are ultimately stored, retrieved, or processed here.
- Offers scalability, durability, and cross‑cloud accessibility.

![](https://github.com/kumbharshruti/CloudComputing-Codtech-21/blob/76404d809d203a1c7db4cb0032adc1be0e6fb485/TASK-3/Architecture.png)


# Setting up Data in S3

- I started this project by setting up a new S3 bucket named nextwork-data-transfer-source-[myname] in the AWS Management Console. I uploaded a few sample files to the bucket to serve as the data source for the upcoming transfer to GCP.

![]()

# Setting up GCP

- Google Cloud Platform is a suite of cloud services by Google, offering storage, compute, databases, and more. I set up a GCP account to create a destination for data from AWS S3 and to use Storage Transfer Service for cross-cloud backups.

![]()

# Storage Transfer

- Data transfers are important for ensuring data is backed up, accessible, and secure across platforms. Using multiple cloud providers has benefits such as higher reliability, cost optimization, and better use of each platform’s strengths.

- The transfer is set up using Storage Transfer Service, which automates data movement between AWS and GCP. We need this service because it handles cross-cloud authentication and avoids manual, error-prone transfers.

- There are two different types of transfers you could set up: batch and event-driven. The difference is that batch runs on a set schedule or once, while event-driven automatically transfers data when changes happen in the source.

![]()

# Granting GCP Access to AWS

- To connect AWS and GCP, I'm using identity federation, which works by granting GCP temporary access to AWS via an IAM role. This is more secure than other methods because it avoids using long-term access keys.

- I created a custom IAM role for GCP’s Storage Transfer Service because it needs secure, read-only access to my S3 bucket. This lets GCP pull data without giving it broader permissions, following the principle of least privilege.

- Within the IAM role, I needed a custom trust policy to securely allow GCP access. The policy uses a subject ID, which uniquely identifies my GCP project’s service account and ensures only it can access the S3 bucket.

![]()
  
# Transferring from S3 to GCS!

- To set up my destination GCS bucket, I selected a region for data storage to improve transfer speed and reduce latency. The storage class was set to Standard, meaning the data will be frequently accessed with high performance and availability.

- I verified my data transfer was successful by checking my GCP Cloud Storage bucket. After the transfer job completed successfully, I navigated to the bucket in the GCP console and refreshed the page. The files from my S3 bucket were listed in GCP.

![]()

# Transfer with a Manifest

- I verified my data transfer was successful by checking my GCP Cloud Storage bucket. After the transfer job completed successfully, I navigated to the bucket in the GCP console and refreshed the page. The files from my S3 bucket were listed in GCP.


# Trial, Error, Success

GCP's free tier includes access to 25+ services like Cloud Storage, Compute Engine, and BigQuery within monthly limits. I also get $300 in credits to spend on other GCP services across the first 90 days of my account.
