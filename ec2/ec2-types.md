# Amazon EC2 Instance Types and Pricing Models

Amazon EC2 offers a wide range of instance types grouped by workload (general purpose, compute, memory, storage, accelerated computing, HPC), and pricing models (On-Demand, Reserved, Spot, Savings Plans, Dedicated Hosts). Choosing the right combination depends on performance needs and cost optimization strategies.

---

## 🖥️ EC2 Instance Types

| **Category** | **Examples** | **Use Cases** |
|--------------|--------------|---------------|
| **General Purpose** | T3, T4g, M6i, M7g | Balanced workloads like web servers, small databases, dev/test environments. |
| **Compute Optimized** | C6i, C7g | High-performance computing, batch processing, media transcoding, gaming servers. |
| **Memory Optimized** | R6i, R7g, X2idn | Large in-memory databases, caching, big data analytics, SAP workloads. |
| **Storage Optimized** | I3, I4i, D3, H1 | High IOPS workloads, NoSQL databases, data warehousing, log processing. |
| **Accelerated Computing** | P4, G5, Inf1 | Machine learning training/inference, GPU rendering, scientific simulations. |
| **High Performance Computing** | Hpc6id, C7i | Large-scale simulations, deep learning, genomics research. |

---

## 💰 EC2 Pricing Models

| **Model** | **Description** | **Best Use Cases** |
|-----------|-----------------|--------------------|
| **On-Demand** | Pay per second/hour with no commitment. | Short-term, unpredictable workloads, testing environments. |
| **Reserved Instances** | 1–3 year commitment with up to 72% savings. | Steady-state workloads like databases, enterprise apps. |
| **Spot Instances** | Up to 90% cheaper, but can be interrupted. | Flexible workloads, batch jobs, CI/CD pipelines, ML training. |
| **Savings Plans** | Flexible pricing model with 1–3 year commitment. | Workloads that can shift across instance families/regions. |
| **Dedicated Hosts** | Physical server dedicated to you. | Compliance-heavy workloads, BYOL (Bring Your Own License) software. |

---

## ⚡ Practical Examples

- **Web Hosting** → General Purpose (M6i) with On-Demand for flexibility.  
- **Machine Learning Training** → Accelerated Computing (P4d) with Spot for cost savings.  
- **Enterprise Database** → Memory Optimized (R7i) with Reserved Instances for predictable workloads.  
- **Big Data Analytics** → Storage Optimized (I4i) with Savings Plans for long-term cost efficiency.  
- **HPC Simulations** → HPC instances (Hpc6id) with Spot for large-scale, interruptible workloads.  

---

## 🚨 Risks & Fixes

- **Spot interruptions** → Use Auto Scaling + checkpointing to resume jobs.  
- **Reserved lock-in** → Analyze workload patterns before committing.  
- **High costs with On-Demand** → Switch to Savings Plans or Reserved Instances.  
- **Performance mismatch** → Use AWS Compute Optimizer to recommend right instance type.  

---

