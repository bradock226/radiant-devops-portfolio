\# RTS-1091 – Security Group Drift Remediation



\## Context

Monitoring alerts flagged unexpected inbound traffic behavior on an EC2 instance

in a production-adjacent AWS environment.



\## Root Cause

A security group ingress rule had been manually modified via the AWS Console,

causing drift from the Terraform source of truth.



\## Actions Taken

\- Reviewed CloudWatch metrics and VPC Flow Logs

\- Executed `terraform plan` to confirm drift

\- Reverted manual changes using Terraform

\- Verified application availability post-change



\## Outcome

\- Terraform state fully reconciled

\- No downtime observed

\- Recommendation made to restrict manual console changes



\## Tools

AWS EC2, VPC, Security Groups, Terraform, AWS CLI, Git



