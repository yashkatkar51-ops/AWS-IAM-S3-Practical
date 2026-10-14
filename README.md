# AWS IAM and Amazon S3 Practical Project

## Project Overview
This project demonstrates hands-on practice with AWS Identity and Access Management (IAM) and Amazon Simple Storage Service (S3). It focuses on identity management, access permissions, bucket security, data protection, and storage management.

## Objectives
- Create IAM users and groups.
- Configure AWS-managed and custom IAM policies.
- Create an EC2 IAM role with restricted S3 read access.
- Verify allowed and denied permissions.
- Configure an S3 bucket with secure access settings.
- Implement object organization, versioning, and recovery.
- Configure a bucket policy, lifecycle rule, and server access logging.
- Understand server-side encryption and access controls.

## Practical Tasks Completed
1. IAM users and groups
2. AWS-managed IAM policies
3. Custom S3 read-only IAM policy
4. EC2 IAM role for S3 access
5. IAM permission verification
6. S3 bucket creation and security
7. Object organization and versioning
8. S3 bucket policy configuration
9. S3 lifecycle rule
10. S3 server access logging
11. Encryption and access control concepts

## Repository Structure
- `README.md` — Project documentation
- `screenshots/` — Practical evidence and test screenshots
- `policies/` — Custom IAM and S3 bucket policy JSON files

## Test Results
Document the actual results of each test.

| Test | Expected Result |
|---|---|---|
| List permitted S3 objects | Allowed |
| Download permitted objects | Allowed |
| Upload using a read-only identity | Denied |
| Delete using a read-only identity | Denied |
| Anonymous/public access | Blocked |

## Key Learnings
- Managing IAM users, groups, roles, and policies.
- Applying least-privilege access to AWS resources.
- Securing S3 buckets and controlling object access.
- Understanding S3 versioning and recovery.
- Understanding lifecycle transitions and server access logging.
- Identifying server-side encryption settings and effective permissions.

## Conclusion
This practical helped me gain hands-on experience with AWS IAM and Amazon S3. I learned how to manage identities, apply access controls, secure storage resources, enable versioning, configure lifecycle rules and logging, and understand encryption. It strengthened my understanding of fundamental AWS cloud security concepts.

## Evidence
Screenshots and policy files are included in this repository for reference.



