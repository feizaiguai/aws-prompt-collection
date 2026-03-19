# Prompt 2: Security Posture Analyzer

**Category**: Security and Compliance
**AWS Services**: IAM, GuardDuty, Security Hub, Config
**Difficulty**: Advanced

## The Prompt

```
You are an AWS Security Architect performing a comprehensive security posture review. Analyze the following AWS account configuration and provide actionable remediation steps.

INPUT - Current IAM Policies (paste your policy JSON or describe):
[Paste IAM policy JSON or describe current access patterns]

INPUT - Network Configuration:
- VPC CIDR: [e.g., 10.0.0.0/16]
- Public subnets: [count and use]
- Security groups: [describe key rules]
- NAT/Internet Gateways: [configuration]

INPUT - Data Classification:
- S3 buckets: [list with contents classification: public/internal/confidential/restricted]
- Databases: [list with data sensitivity level]
- Secrets management: [current approach]

ANALYSIS TASKS:
1. IAM AUDIT
   - Identify over-privileged policies (any use of "*" in actions or resources)
   - Flag policies missing conditions (e.g., MFA, IP restrictions, time-based)
   - Detect unused roles/users (if age information provided)
   - Generate least-privilege replacement policies

2. NETWORK SECURITY
   - Identify security group rules allowing 0.0.0.0/0 on non-standard ports
   - Check for missing VPC Flow Logs
   - Validate NACLs complement security groups
   - Recommend VPC endpoint usage

3. DATA PROTECTION
   - Verify encryption at rest and in transit
   - Check S3 bucket policies for public access risks
   - Validate backup and versioning configurations
   - Recommend AWS KMS key rotation policies

4. DETECTION AND MONITORING
   - Recommend GuardDuty configuration
   - Define Security Hub standards to enable
   - Create CloudWatch alarm definitions for security events
   - Generate AWS Config rules for continuous compliance

OUTPUT FORMAT:
For each finding:
- Severity: CRITICAL / HIGH / MEDIUM / LOW
- Current State: What is wrong
- Risk: What could happen
- Remediation: Exact AWS CLI commands or IaC snippets to fix
- Verification: How to confirm the fix worked

Prioritize findings by severity. Provide an executive summary at the top.
```

## Use Case

SOC2/HIPAA audit preparation. Security teams can use this prompt to get an instant security review of their AWS environment with specific CLI commands to fix each issue.
