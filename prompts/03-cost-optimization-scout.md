# Prompt 3: Cost Optimization Scout

**Category**: Cost Optimization / FinOps
**AWS Services**: Cost Explorer, Compute Optimizer, Trusted Advisor
**Difficulty**: Intermediate

## The Prompt

```
You are an AWS FinOps consultant specializing in cloud cost optimization. Analyze my AWS spending patterns and generate a comprehensive cost reduction plan.

MONTHLY SPEND BREAKDOWN (provide your data):
- EC2 instances: $[amount] ([instance types and counts])
- RDS databases: $[amount] ([engine, instance class])
- S3 storage: $[amount] ([total GB, access patterns])
- Data Transfer: $[amount] ([inter-region, internet egress])
- Lambda: $[amount] ([invocations/month, avg duration])
- Other services: $[amount] ([list])

USAGE PATTERNS:
- Business hours: [e.g., Mon-Fri 8AM-6PM EST]
- Peak traffic: [when and how much above baseline]
- Dev/Test environments: [how many, always-on?]
- Data lifecycle: [how long is data retained?]

OPTIMIZATION ANALYSIS:
1. COMPUTE RIGHT-SIZING
   - Analyze instance selection vs actual CPU/memory utilization
   - Recommend specific instance type changes with projected savings
   - Identify candidates for Graviton (ARM) migration
   - Calculate Savings Plans vs Reserved Instance recommendations

2. SCHEDULING OPTIMIZATION
   - Identify non-production resources running 24/7
   - Generate AWS Instance Scheduler configuration
   - Calculate savings from stop/start automation

3. STORAGE OPTIMIZATION
   - Recommend S3 Intelligent-Tiering or lifecycle policies
   - Identify unattached EBS volumes and stale snapshots
   - Optimize RDS storage (gp3 vs io1, Aurora vs standard)

4. ARCHITECTURE IMPROVEMENTS
   - Spot Instance opportunities for fault-tolerant workloads
   - Serverless migration candidates (EC2 to Lambda/Fargate)
   - CloudFront + S3 for static content
   - NAT Gateway alternatives (VPC endpoints, NAT instances for dev)

5. QUICK WINS (implementable today)
   - List top 5 changes that save the most with least effort
   - Provide exact AWS CLI commands for each

OUTPUT FORMAT:
| Optimization | Current Cost | Projected Cost | Monthly Savings | Effort | Priority |
Generate a 30/60/90 day implementation roadmap.
```

## Use Case

Monthly FinOps review for any AWS-heavy organization. Produces a prioritized action plan with exact commands and projected ROI.
