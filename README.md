# Platinum Castle Secure Client Portal

> 🔒 **Note:** The source code for this project is proprietary and closed-source due to commercial NDAs. This repository serves as a technical showcase, architecture breakdown, and demonstration of the production system.

## 📺 [Watch the System Demo](https://www.youtube.com/watch?v=zEgYVuOZJtU)

## 🚀 Project Overview
**Platinum Castle Accounting** required a secure, compliant way to exchange sensitive tax documents with clients, replacing insecure email workflows.

I architected and deployed a **Serverless Client Portal** using **Next.js 16** and **AWS**. The system is currently in production, serving **~150 clients** and has reduced manual administrative follow-up time by **40%**.

## 🛠 Technical Architecture

### Core Stack
* **Frontend:** Next.js 16 (App Router) deployed as a PWA on AWS Amplify.
* **Identity:** AWS Cognito (MFA & Role-Based Access Control).
* **Storage:** AWS S3 (Server-Side Encryption with KMS).
* **Database:** Amazon DynamoDB (Single-Table Design).
* **Compute:** AWS Lambda (Node.js) & Resend API for automation.

### Key Implementation Details
1.  **Zero-Trust File Storage:** Files are uploaded directly to private S3 buckets using signed URLs. The backend never handles the file stream, ensuring high performance and security.
2.  **Automated Workflows:** AWS Lambda triggers listen to DynamoDB streams. When a client uploads a document, the system automatically updates the status and notifies staff via the Resend API.
3.  **Offline-First Mobile Support:** Built as a Progressive Web App (PWA) to allow clients to access documents on mobile devices with poor connectivity.

## 🔒 Security & Compliance
* **Encryption:** All data is encrypted at rest (AWS KMS) and in transit (TLS 1.3).
* **Access Control:** Strict IAM policies enforce "Least Privilege" access for backend services.
* **Session Management:** Secure HttpOnly cookies with CSRF protection.

---
### 📬 Contact
**Architected by [Ariel Hartal]**
[(https://www.linkedin.com/in/ariel-hartal-711320278/)]
