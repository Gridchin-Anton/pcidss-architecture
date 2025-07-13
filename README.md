# PCI-DSS Compliant Multi-Region Payment Platform on AWS EKS

A **production-ready**, multi-region AWS EKS platform designed for FinTech applications requiring PCI-DSS compliance. Implements tokenization, secure CI/CD, and cost-optimized infrastructure.

## 🔍 Overview
- **Key Features**:
  - ✅ **PCI-DSS Controls**: Encryption (Req. 4), Logging (Req. 10), Vulnerability Scans (Req. 11)
  - 🌐 **Multi-Region Resilience**: Active-passive failover between `us-east-1` and `eu-west-1`
  - 🔒 **Zero-Trust Security**: OPA/Gatekeeper policies, KMS tokenization, IAM least privilege
  - 💰 **Cost Optimization**: Spot instances, RDS Reserved Instances (~40% savings)

## 🛠️ Technologies
| **Category**       | **Tools**                                                                 |
|--------------------|--------------------------------------------------------------------------|
| **Infrastructure** | Terraform, AWS EKS, VPC Peering, RDS PostgreSQL                         |
| **Security**       | OWASP ZAP, Trivy, Semgrep, TerraScan, AWS KMS (tokenization)            |
| **CI/CD**          | GitLab CI/CD with dynamic testing in isolated EKS cluster                |
| **Monitoring**     | Grafana (metrics), CloudWatch (logs), Prometheus (audit trails)          |

## 📂 Repository Structure
```
.
├── terraform/           # Multi-region infra (EKS, RDS, VPC)
├── kubernetes/          # PCI-hardened manifests + OPA policies
├── gitlab-ci/           # Secure pipeline (scan → build → test → deploy)
├── docs/                # Architecture diagrams, PCI mappings, cost analysis
└── payment-app/         # Mock Python FastAPI payment service (tokenization demo)
```

