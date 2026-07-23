# aws-training
## Network Architecture Decisions

This project’s VPC design follows AWS best practices for resilience, security, and cost‑efficiency.  
Below are the key decisions and the reasoning behind them.

---

### **1. Multi‑AZ Deployment (High Availability & Resilience)**

The VPC spans **two Availability Zones (AZs)**: `eu-north-1a` and `eu-north-1b`.

**Why this matters:**
- Each AZ is an isolated failure domain.
- If one AZ experiences a power, network, or hardware failure, workloads in the other AZ remain available.
- Enables high‑availability patterns (ALB, ASG, RDS Multi‑AZ).
- Eliminates single points of failure at the infrastructure layer.

This ensures the network is resilient and production‑ready.

---

### **2. Gateway Endpoints for S3 & DynamoDB (Secure, Free, NAT‑Bypass)**

The VPC uses **Gateway Endpoints** for:
- **Amazon S3**
- **Amazon DynamoDB**

**Why this matters:**
- **Zero cost** — Gateway endpoints are free.
- **Traffic stays on AWS’s private backbone** (no internet traversal).
- **Avoids NAT Gateway data processing charges** (~£0.045/GB in eu‑north‑1).
- **Improved security** — S3 buckets can be restricted to only allow access via the VPC endpoint.
- **Lower latency** compared to routing through NAT.

This design keeps private subnet traffic private and reduces operational cost.

---

### **3. NAT Gateway Instead of NAT Instance (Managed, Scalable, No Single Point of Failure)**

A **managed NAT Gateway** is deployed in the public subnet of `eu-north-1a`.

**Why this matters:**
- Fully managed by AWS — no patching, no OS maintenance.
- Highly available within the AZ.
- Automatically scales up to 45 Gbps.
- No single EC2 instance acting as a fragile bottleneck.
- More secure — no SSH access, no custom iptables, no AMI updates.

Using NAT Gateway ensures reliability and simplicity.

---


