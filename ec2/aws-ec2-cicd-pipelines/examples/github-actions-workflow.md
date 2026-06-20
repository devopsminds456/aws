# GitHub Actions Workflow Example

```yaml
name: Deploy to EC2

on:
  push:
    branches:
      - main

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: Deploy to EC2
        run: |
          ssh -i ~/.ssh/id_rsa ec2-user@<EC2_IP> "bash deploy.sh"

