# Prompt 4: Serverless API Architect with Bedrock AI

**Category**: AI Workflows / Developer Tools
**AWS Services**: Lambda, API Gateway, DynamoDB, Bedrock, Step Functions
**Difficulty**: Advanced

## The Prompt

```
You are an AWS Solutions Architect specializing in serverless and AI-powered applications. Design and generate a production-ready serverless API with integrated AI capabilities.

APPLICATION REQUIREMENTS:
- API Purpose: [e.g., "Customer support chatbot API with conversation history"]
- Expected load: [requests/second at peak]
- Data model: [describe entities and relationships]
- AI features needed: [e.g., "text generation, sentiment analysis, document summarization"]
- Authentication: [Cognito / API Key / IAM / Custom]

GENERATE THE FOLLOWING:

1. API DESIGN (OpenAPI 3.0 spec)
   - RESTful endpoints with proper HTTP methods
   - Request/response schemas with validation
   - Error response standardization (RFC 7807)
   - Pagination for list endpoints

2. LAMBDA FUNCTIONS (Python 3.12)
   - Each endpoint as a separate function
   - Proper error handling with structured logging
   - Environment variable configuration
   - Lambda Powertools integration (logging, tracing, metrics)
   - Cold start optimization (lazy loading, connection pooling)

3. AMAZON BEDROCK INTEGRATION
   - Model selection rationale (Claude vs Titan vs Llama)
   - Prompt templates stored in DynamoDB
   - Response streaming for long generations
   - Token usage tracking and cost estimation
   - Fallback model configuration

4. INFRASTRUCTURE (SAM template)
   - API Gateway with throttling and WAF
   - DynamoDB tables with proper key design
   - IAM roles following least privilege
   - CloudWatch dashboards and alarms
   - X-Ray tracing enabled

5. CI/CD PIPELINE
   - GitHub Actions workflow
   - SAM build and deploy stages
   - Integration test suite
   - Canary deployment configuration

CONSTRAINTS:
- All responses under 10 seconds (P99)
- Less than $100/month at 10K daily requests
- HIPAA/SOC2 considerations documented
- No hardcoded credentials
```

## Use Case

Any team building AI-powered APIs on AWS. This single prompt generates the entire project scaffold from API design to CI/CD, following all AWS best practices.
