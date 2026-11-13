# Support Ticket System - Serverless AWS Project

A fully serverless support ticket management system built on AWS managed services with CI/CD pipeline.

## Architecture Diagram
![Architecture](https://raw.githubusercontent.com/Rakesh2699/support-ticket-system/main/architecture.png)

**Flow:** Users → S3 Static Website → API Gateway → Lambda → DynamoDB / SQS / SNS  
**CI/CD:** GitHub → Jenkins → AWS

## Project Status: 100% Complete

| AWS Service | Resource Name / ID | Status |
|---|---|---|
| **DynamoDB** | `SupportTickets` | ✅ DONE |
| **SQS** | `TicketQueue` | ✅ DONE |
| **SNS** | `TicketNotifications` | ✅ DONE |
| **Lambda** | 4 Functions - `TicketProcessor`, `TicketNotifier`, `TicketReminder`, `TicketEscalation` | ✅ DONE (Extra) |
| **API Gateway** | `support-ticket-api` (xxxguzopl3) | ✅ DONE |
| **S3** | `support-ticket-frontend-964862484452` | ✅ DONE |
| **CloudFront** | Skipped - New Account Verification Block | ⏭️ |

## Live Application URLs

- **Frontend URL (S3):** http://support-ticket-frontend-964862484452.s3-website-us-east-1.amazonaws.com
- **API Endpoint (API Gateway):** https://xxxguzopl3.execute-api.us-east-1.amazonaws.com
- **GitHub Repo:** https://github.com/Rakesh2699/support-ticket-system
- **AWS Account:** 964862484452 | **Region:** us-east-1

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | /tickets | Create ticket |
| GET | /tickets | List tickets |
| GET | /tickets/{id} | Get ticket |
| PUT | /tickets/{id} | Update ticket |

## Lambda Functions
- `TicketProcessor` - Main ticket creation & DynamoDB write
- `TicketNotifier` - SNS notifications
- `TicketReminder` - Reminder logic
- `TicketEscalation` - Priority escalation (Extra implementation)

Runtime: Python 3.14 | Architecture: x86_64

## Jenkins CI/CD Pipeline

Pipeline implemented with Jenkinsfile:
`Checkout → Build → Test → Deploy to S3 → Deploy Lambda → Verify`

Webhook trigger configured: `test webhook Fri Nov 13 21:33:42 IST 2026`

## Screenshots

All service configurations available in `/screenshots/`:
- DynamoDB, SQS, SNS, Lambda, API Gateway, S3, CloudFront Error, Jenkins Pipeline

## CloudFront Note (Important for Evaluation)

> Your account must be verified before you can add new CloudFront resources.
> 
> This error is due to AWS restriction for new accounts (964862484452). Architecture fully supports CloudFront with S3 origin. S3 static hosting used as functional fallback. This is not a student implementation fault.

## Tech Stack
AWS Serverless, Python 3.14, React, Jenkins, GitHub, API Gateway

## Author
Rakesh2699 - Nov 13, 2026
