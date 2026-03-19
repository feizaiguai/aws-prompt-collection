# Prompt 5: Disaster Recovery Planner

**Category**: Infrastructure / Reliability
**AWS Services**: Route 53, S3, RDS, Multi-Region, AWS Backup
**Difficulty**: Advanced

## The Prompt

```
You are an AWS Disaster Recovery specialist. Design a comprehensive DR plan for my application based on the specified RPO/RTO requirements.

APPLICATION PROFILE:
- Architecture: [e.g., "3-tier web app: ALB then ECS Fargate then Aurora PostgreSQL"]
- Primary region: [e.g., us-east-1]
- Current data volume: [e.g., "500 GB database, 2 TB S3"]
- Daily data change rate: [e.g., "approximately 5 GB new data, approximately 20 GB modified"]
- Business criticality: [Tier 1 (mission-critical) / Tier 2 / Tier 3]

DR REQUIREMENTS:
- Target RPO: [e.g., "less than 1 hour", maximum acceptable data loss]
- Target RTO: [e.g., "less than 4 hours", maximum acceptable downtime]
- Budget constraint: [e.g., "DR infrastructure less than 30% of primary cost"]
- Compliance: [any regulatory DR requirements]

GENERATE:

1. DR STRATEGY SELECTION
   - Evaluate all 4 AWS DR strategies against requirements:
     a. Backup and Restore
     b. Pilot Light
     c. Warm Standby
     d. Multi-Site Active/Active
   - Recommend optimal strategy with cost comparison
   - Justify selection against RPO/RTO targets

2. DR ARCHITECTURE
   - Secondary region resource specification
   - Data replication configuration (async/sync, tools)
   - DNS failover with Route 53 health checks
   - Architecture diagram (mermaid syntax)

3. RUNBOOK
   - Automated failover procedure (Step Functions workflow)
   - Manual failover checklist
   - Failback procedure after recovery
   - Communication plan template

4. TESTING PLAN
   - Quarterly DR drill schedule
   - Automated chaos engineering tests (AWS FIS)
   - Success/failure criteria
   - Post-drill review template

5. COST ANALYSIS
   - DR infrastructure monthly cost breakdown
   - Data transfer costs between regions
   - Storage costs for replicated data
   - Total DR cost as percentage of production

OUTPUT:
- Complete runbook in markdown
- CloudFormation/CDK for DR infrastructure
- Route 53 health check configurations
- AWS Backup plan definitions
```

## Use Case

Enterprise DR planning and compliance. Generates a complete, auditable DR plan with infrastructure code, runbooks, and testing procedures.
