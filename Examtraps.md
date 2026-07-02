# AWS Certified Solutions Architect – Associate (SAA‑C03)  
### Exam Overview & Common Traps

The **AWS Certified Solutions Architect – Associate (SAA‑C03)** exam validates your ability to design secure, resilient, high‑performing, and cost‑optimized architectures using AWS services. It is aligned with the **AWS Well‑Architected Framework** and is intended for individuals with at least one year of hands‑on AWS experience.

---

## 📌 Exam Structure

- **65 questions total**
  - 50 scored
  - 15 unscored (mixed randomly)
- **Formats:** Multiple choice & multiple response  
- **Duration:** 130 minutes  
- **Passing score:** 720 / 1000  
- **No negative marking**

---

# 📚 Exam Domains

## 1. Design Secure Architectures (30%)

Focus areas:
- IAM, identity federation, SCPs
- Network security (VPC, NACLs, Security Groups)
- Application protection (WAF, Shield)
- Encryption (KMS, S3 encryption, key rotation)
- Secure data access patterns

---

## 2. Design Resilient Architectures (26%)

Focus areas:
- Multi‑AZ vs Multi‑Region strategies
- Auto Scaling & health checks
- Decoupling (SQS, SNS, EventBridge)
- Fault‑tolerant designs
- Disaster recovery patterns

---

## 3. Design High‑Performing Architectures (24%)

Focus areas:
- Compute selection (EC2 families, Lambda, ECS/EKS)
- Storage performance (EBS types, S3 performance tuning)
- Database performance (RDS, Aurora, DynamoDB)
- Caching (ElastiCache, CloudFront)
- Networking performance (ALB/NLB, Global Accelerator)

---

## 4. Design Cost‑Optimized Architectures (20%)

Focus areas:
- Right‑sizing compute & storage
- Pricing models (On‑Demand, Reserved, Spot, Savings Plans)
- Data transfer cost optimization
- Managed services vs self‑managed tradeoffs

---

# ⚠️ Common Exam Traps & What to Watch Out For

## 1. High Availability vs Fault Tolerance
- **HA = Multi‑AZ**
- **FT = Multi‑Region + redundancy**
Many candidates choose HA when FT is required.

---

## 2. S3 Storage Class Confusion
Watch out for:
- Standard‑IA vs One Zone‑IA  
- Glacier Instant vs Flexible Retrieval  
- Lifecycle transitions  
Cost‑optimization questions often hinge on subtle differences.

---

## 3. Data Transfer Costs
Key points:
- Inter‑AZ transfer is **not free**
- NAT Gateway processing fees add up quickly
- CloudFront → S3 is free  
Expect cost‑related trick questions.

---

## 4. IAM vs Resource‑Based Policies
Examples:
- S3 bucket policies = resource‑based  
- IAM roles = identity‑based  
Cross‑account access questions often test this distinction.

---

## 5. Choosing the Wrong Load Balancer
- **ALB:** HTTP/HTTPS, routing rules  
- **NLB:** TCP/UDP, extreme performance  
- **GWLB:** Security appliances  
Protocol hints in the question determine the correct answer.

---

## 6. DynamoDB Pitfalls
Watch for:
- Hot partitions (bad partition key design)
- RCU/WCU vs On‑Demand
- Streams vs TTL vs Global Tables  
Performance questions frequently target DynamoDB.

---

## 7. VPC Endpoint Confusion
- **Gateway endpoints:** S3 & DynamoDB  
- **Interface endpoints:** Everything else  
A very common exam trap.

---

## 8. Over‑engineering Multi‑Region
Use multi‑region only when:
- Global users  
- DR requirements  
- Extreme availability  
Most workloads only need Multi‑AZ.

---

## 9. Encryption Misunderstandings
- KMS key rotation vs AWS‑managed rotation  
- Envelope encryption  
- Client‑side vs server‑side encryption  
Expect compliance‑driven scenarios.

---

## 10. Misreading Keywords
AWS exam questions often hinge on:
- “Most cost‑effective”
- “Least operational overhead”
- “Highly available”
- “Fault tolerant”
- “Simplest architecture”
These keywords change the correct answer entirely.

---

# 🎯 Final Tips

- Prefer **managed services** unless the question demands control.
- Align every answer with the **Well‑Architected Framework**.
- Eliminate options that add unnecessary complexity.
- Look for hidden constraints in the question (budget, compliance, performance).
