# 🌐 EC2 Web Hosting Use Case

## 📖 Overview
Amazon EC2 can be used to host websites and APIs by providing scalable compute resources. It allows you to deploy applications quickly, configure networking, and integrate with other AWS services for a production‑ready environment.

---

## 🛠️ Architecture Components
- **EC2 Instance** → Runs the web server (Apache, Nginx, Node.js, etc.).  
- **Security Groups** → Control inbound/outbound traffic (e.g., allow HTTP/HTTPS).  
- **Elastic IP** → Provides a static public IP for consistent access.  
- **Elastic Load Balancer (ELB)** → Distributes traffic across multiple EC2 instances.  
- **Auto Scaling** → Automatically adjusts capacity based on demand.  
- **CloudWatch** → Monitors performance and sets alarms.  

---

## 🚀 Example Setup
1. Launch an EC2 instance with Amazon Linux or Ubuntu.  
2. Attach a security group allowing inbound traffic on ports 80 (HTTP) and 443 (HTTPS).  
3. Use **User Data** to install and configure Apache/Nginx at boot:

```bash
#!/bin/bash
yum update -y
yum install -y httpd
systemctl enable httpd
systemctl start httpd
echo "<h1>My Website on EC2</h1>" > /var/www/html/index.html

4. Assign an Elastic IP for stable access.

5. (Optional) Add a Load Balancer + Auto Scaling group for high availability.
============================================================================

Best Practices

1. Use IAM roles for secure access to S3 or other AWS services.

2. Enable HTTPS with SSL/TLS certificates via AWS Certificate Manager.

3. Configure Auto Scaling to handle traffic spikes.

4. Store logs in CloudWatch Logs or S3 for auditing.

5. Apply patches and updates regularly to the OS and web server.

=================================================================

# ⚡ EC2 Troubleshooting Guide

## 📖 Overview
Amazon EC2 instances can encounter issues related to connectivity, configuration, performance, and cost. This guide outlines common problems, their causes, and recommended fixes.

---

## 🚨 Common Issues & Fixes

### 1. Instance Launch Failure
- **Cause:** Invalid AMI, unsupported instance type, or quota limits.
- **Fix:**
  - Verify AMI compatibility with the chosen instance type.
  - Request a quota increase from AWS.
  - Select a supported instance type in the region.

---

### 2. SSH Connection Error (Linux Instances)
- **Cause:** Wrong key pair, closed port 22, or misconfigured security group.
- **Fix:**
  - Ensure you’re using the correct private key (`.pem` file).
  - Open port 22 in the security group.
  - Check NACL rules and routing tables.

---

### 3. RDP Connection Issue (Windows Instances)
- **Cause:** Windows firewall blocking, wrong password, or closed port 3389.
- **Fix:**
  - Reset the Windows password via Systems Manager.
  - Open port 3389 in the security group.
  - Verify firewall settings inside the instance.

---

### 4. Unreachable Instance
- **Cause:** Failed status checks, corrupted OS, or misconfigured networking.
- **Fix:**
  - Use the EC2 Serial Console for troubleshooting.
  - Check VPC routing tables and NACLs.
  - Restore the instance from a backup AMI.

---

### 5. Wrong Boot Volume
- **Cause:** Incorrect EBS attachment or AMI misconfiguration.
- **Fix:**
  - Detach the incorrect volume.
  - Reattach the correct root volume.
  - Rebuild the AMI if necessary.

---

### 6. High Costs
- **Cause:** Running On-Demand instances continuously.
- **Fix:**
  - Switch to Reserved or Spot Instances.
  - Use instance scheduler to stop/start during off-hours.
  - Right-size workloads using AWS Compute Optimizer.

---

## ✅ Best Practices
- Always **tag resources** for cost tracking.
- Use **IAM roles** instead of embedding credentials.
- Enable **CloudWatch monitoring** for CPU, memory, and disk health.
- Automate **EBS snapshot backups** with lifecycle policies.
- Apply **least privilege security groups** to minimize attack surface.

---

