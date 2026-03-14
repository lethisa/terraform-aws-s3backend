# S3 Backend Module

This module provisions the required AWS resources to support a Terraform remote backend using Amazon S3 for state storage and DynamoDB for state locking.
The backend infrastructure created by this module enables teams to safely store and manage Terraform state in a centralized and reliable way.

## Features

- Creates an Amazon S3 bucket to store Terraform state files
- Enables bucket versioning to protect against accidental state loss
- Configures server-side encryption using AWS KMS
- Creates a DynamoDB table for Terraform state locking
- Provides necessary IAM role and policy for Terraform operations
- Outputs backend configuration values for easy integration

## Why use a Remote Backend

Using a remote backend improves Terraform workflows by providing:

- State locking to prevent concurrent modifications
- Centralized state management
- State version history
- Improved collaboration across teams
- Better disaster recovery

## Resources created

This module provisions the following AWS resources:

- S3 bucket for Terraform state
- S3 bucket versioning configuration
- S3 server-side encryption configuration
- DynamoDB table for state locking
- IAM role and policy for backend access
- KMS key for encryption

## Outputs

The module exposes several outputs that can be used to configure the Terraform backend:

- bucket – Name of the S3 bucket storing Terraform state
- region – AWS region where the backend resources are deployed
- role_arn – IAM role ARN used for Terraform access
- dynamodb_table – DynamoDB table used for state locking

## Use Case

This module is typically used during the initial bootstrap phase of a Terraform infrastructure. Once the backend resources are created, Terraform configurations can be updated to use the remote S3 backend.
