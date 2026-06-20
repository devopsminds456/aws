# GitHub Actions with EC2

## Overview
GitHub Actions can deploy directly to EC2 after builds/tests.

## Steps
1. Create workflow YAML in `.github/workflows`.
2. Configure SSH or use AWS CLI with IAM role.
3. Deploy artifacts to EC2.

## Benefits
- Native GitHub integration
- Easy to set up

## Risks
- Secrets must be managed securely.

