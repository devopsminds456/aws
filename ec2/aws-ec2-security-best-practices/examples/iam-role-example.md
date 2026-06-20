# IAM Role Example

## Scenario
EC2 instance needs access to S3 bucket.

## Action
- Created IAM role with S3 read-only policy.
- Attached role to EC2 instance.

## Result
Instance accessed S3 securely without static credentials.

