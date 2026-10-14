# AWS IAM and Amazon S3 Practical 

## Student Details
- **Name:Yash Katkar** 
- **Batch:MCA 24_JUNE** 

## Project Overview
This repository documents my hands-on AWS IAM and Amazon S3 practical work. It includes screenshots of the tasks I completed, explanations of key concepts, and a record of permission tests.

## Objectives
- Create IAM users and groups.
- Attach AWS-managed IAM policies.
- Create and configure a custom S3 read policy.
- Create an EC2 role with restricted S3 read access.
- Test allowed and denied S3 actions.
- Create and secure an S3 bucket.
- Organize objects and enable versioning.
- Configure an S3 bucket policy.
- Configure an S3 lifecycle rule.
- Configure server access logging.
- Review encryption and access controls.

## Practical Tasks and Explanations

### Task 1: Create IAM Users and Groups
Create the `developer-user` and `tester-user` IAM users, along with the `Developers` and `Testers` groups. Add each user to the corresponding group.

**Purpose:** Organize identities so permissions can be managed by group.

### Task 2: Attach IAM Policies
- `AmazonS3ReadOnlyAccess` allows permitted S3 listing and read operations.
- `AmazonS3FullAccess` provides broad S3 permissions, including operations such as reading, uploading, and deleting objects, subject to other applicable controls.

**Purpose:** Compare read-only access with broader S3 access.

### Task 3: Create a Custom IAM Policy
The practical asks for a customer-managed policy named `CustomS3ReadPolicy` that allows listing the practical bucket and reading its objects only, without allowing uploads, overwrites, or deletions.

**Evidence/status:screenshots/custom-iam-policy-json.png**

### Task 4: Create an IAM Role for EC2
Create an `EC2S3ReadRole` role trusted by the EC2 service, with permission to read objects from the practical bucket only. Long-term access keys should not be created or stored for the EC2 instance.

**Purpose:** Allow an EC2 workload to access only the required S3 resources using a role.

### Task 5: Verify IAM Permissions
Record the results of your actual tests below. Replace each placeholder with the result you observed; do not mark an action as allowed or denied without testing it.

| Action tested | Expected result | Actual result |
|---|---|---|
| List permitted S3 objects | Allowed | screenshots/iam-user-list-objects-access.png |
| Download a permitted object | Allowed | screenshots/iam-user-permission-test-results.png |
| Upload using a read-only identity | Denied | screenshots/permission-test-result.png] |
| Delete using a read-only identity | Denied | screenshots/permissions-test-results.png |

### Task 6: Create and Secure an S3 Bucket
Create a uniquely named S3 bucket in the assigned AWS Region, keep S3 Block Public Access enabled, enable default server-side encryption, and upload three sample files.

**Purpose:** Store objects while applying basic security protections.

### Task 7: Organize Objects and Enable Versioning
Create the `documents/`, `images/`, and `backups/` prefixes, place suitable sample objects under each, and enable bucket versioning. Upload `report.txt`, change its content, upload it again using the same key, and demonstrate restoring the earlier version as the current version.

**Explanation:** S3 Versioning preserves multiple versions of an object, helping recover earlier content after an overwrite or other change.

### Task 8: Configure an S3 Bucket Policy
Configure the bucket policy to allow the intended `developer-user` principal to read objects from the bucket. Use the correct bucket and object ARNs and keep anonymous/public access blocked.

**Explanation:** An S3 bucket policy is a resource-based policy attached to a bucket. It defines which principals can perform specified actions on that bucket and its objects. Test access as the intended principal and verify that public access remains blocked.

**Evidence/status:screenshots/custom-s3-policy.png**.

### Task 9: Configure a Lifecycle Rule
Create and enable a lifecycle rule named `BackupTransitionRule` for objects under the `backups/` prefix, configured to transition eligible objects to S3 Standard-IA after 30 days.

**Why might an object not transition immediately?** Lifecycle processing is asynchronous, so changes do not happen immediately. Transition eligibility, object size, and applicable storage-duration charges should also be considered.

### Task 10: Configure Server Access Logging
Configure a separate destination bucket for access logs and enable server access logging on the source bucket.

**Why might logs not appear immediately?** Log delivery can take time and is best-effort. Do not claim delivery was verified until a log object appears in the destination bucket.

### Task 11: Explain Encryption and Access Controls
- **Server-side encryption:** Protects object data at rest. Record the encryption setting shown in the Properties page of one of your uploaded objects.
- **IAM policy vs. bucket policy:** An IAM policy is attached to an IAM identity, such as a user, group, or role. A bucket policy is attached to an S3 bucket and specifies access for principals.
- **Block Public Access:** Helps prevent accidental public exposure by blocking public access configurations.



## Repository Contents
- `README.md` — Project documentation and task explanations.
- `screenshots/` — Practical screenshots (add this folder and your images).

## Conclusion
This practical covers important AWS IAM and S3 concepts, including identity and permission management, least-privilege access, secure object storage, versioning, lifecycle management, logging, and encryption. The screenshots and test results in this repository should reflect the configurations and checks actually completed.

