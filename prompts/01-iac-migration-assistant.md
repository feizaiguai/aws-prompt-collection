# Prompt 1: IaC Migration Assistant

**Category**: Infrastructure as Code
**AWS Services**: CloudFormation, AWS CDK, Terraform
**Difficulty**: Intermediate

## The Prompt

```
You are an AWS Infrastructure as Code (IaC) migration specialist. I need to convert an existing manually-provisioned AWS infrastructure into automated IaC templates.

CURRENT INFRASTRUCTURE (describe your setup):
- [List your manually created AWS resources here, e.g., "3 EC2 instances (t3.medium) in us-east-1, 1 RDS PostgreSQL db.r5.large, 1 Application Load Balancer, 2 S3 buckets, VPC with 3 subnets"]

TARGET IaC TOOL: [CloudFormation / CDK (TypeScript) / Terraform]

REQUIREMENTS:
1. Generate complete IaC template(s) that reproduce this infrastructure exactly
2. Follow AWS Well-Architected Framework best practices:
   - Use parameter/variable files for environment-specific values
   - Implement proper tagging strategy (Environment, Project, Owner, CostCenter)
   - Apply least-privilege IAM policies
   - Enable encryption at rest for all data stores
   - Configure proper security groups with minimal required ports
3. Include a deployment script with these phases:
   - Pre-deployment validation (lint + dry-run)
   - Staged deployment (network then data then compute then application)
   - Post-deployment smoke tests
4. Add inline comments explaining AWS-specific design decisions
5. Generate a migration checklist with rollback procedures

OUTPUT FORMAT:
- Main template file(s) with full resource definitions
- Parameters/variables file with sensible defaults
- Deployment script (bash)
- Migration checklist (markdown)
- Architecture diagram description (mermaid syntax)

CRITICAL CONSTRAINTS:
- Do NOT use deprecated resource types
- Ensure all resources have DeletionPolicy/prevent_destroy where appropriate
- Include CloudWatch alarms for critical metrics
- Use AWS Secrets Manager for any credentials
```

## Use Case

When teams need to migrate from manually-provisioned ("ClickOps") AWS infrastructure to reproducible, version-controlled IaC templates. This is the #1 pain point for growing startups who initially deployed via the AWS Console.

## Expected Output

The prompt generates a complete IaC migration package including:
- Full resource templates with proper dependencies
- Environment-specific parameter files (dev/staging/prod)
- Automated deployment script with validation gates
- Architecture diagram in Mermaid syntax
- Pre/post migration checklist
