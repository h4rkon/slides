# FinOps in Azure

## Topics to Cover for Efficient FinOps
- Understanding Azure Pricing and Cost Management Tools
- Budgeting and Cost Allocation
- Cost Optimization Practices
- Operational Efficiency
- Reporting and Analysis
- Governance and Policy Management
- Culture and Change Management
- Continuous Improvement
- Leverage AI and Machine Learning

## Azure Tooling for FinOps
- Azure Cost Management and Billing
- Azure Advisor
- Azure Pricing Calculator
- Azure Budgets
- Azure Policy
- Azure Blueprints
- Power BI
- Azure Automation
- Azure Logic Apps
- Azure Monitor
- Azure Reserved Virtual Machine Instances

# Multi-Cloud with Azure and AWS

## Considerations for Platform Engineering Teams
- Unified Governance and Compliance
- Integrated Cost Management and FinOps
- Cross-Cloud Identity and Access Management (IAM)
- Interoperability and Portability
- Network Architecture and Connectivity
- Centralized Logging and Monitoring
- Consistent Deployment and Automation
- Cross-Cloud Data Management
- Skill Development and Team Structure
- Strategic Vendor Management
- Disaster Recovery and Business Continuity
- Security Posture and Threat Management

# Centralizing FinOps and Logging in Multi-Cloud

## Centralizing FinOps
- Unified Cost Management Platform
- Implement Tagging Standards
- Budgeting and Forecasting
- Cost Optimization Practices
- Cross-Cloud FinOps Reporting
- FinOps Culture

## Centralizing Logging
- Centralized Logging Solution
- Consistent Log Format
- Automated Log Collection
- Security and Compliance
- Retention Policies
- Advanced Analytics and Machine Learning

# Third-Party Tools for FinOps in Single and Multi-Cloud

## Benefits
- Enhanced Cost Visibility and Reporting
- Advanced Cost Optimization Recommendations
- Budget Management and Forecasting
- Governance and Policy Enforcement
- Integration Capabilities

## Suitable Third-Party Tools and Comparison

### CloudHealth by VMware
- **Focus:** Comprehensive cloud cost management, security, and governance.
- **Key Features:** 
  - Detailed cost analysis and reporting.
  - Optimization for rightsizing and reserved instances.
  - Governance and compliance frameworks.
- **Best For:** Deep cost optimization and robust governance.

### Apptio Cloudability
- **Focus:** Cloud financial management with an emphasis on business value.
- **Key Features:** 
  - Advanced budgeting and forecasting.
  - Total Cost of Ownership (TCO) analysis.
  - Rightsizing and Reserved Instance management.
- **Best For:** Aligning cloud spending with business outcomes.

### Flexera
- **Focus:** Hybrid and multi-cloud management, including IT asset management.
- **Key Features:** 
  - Cost optimization for cloud and on-premises.
  - Cloud migration planning.
  - Software license optimization.
- **Best For:** Complex hybrid environments and software license management.

## Considerations for Choosing Among Tools
- Evaluate your cloud environment's complexity.
- Determine your focus between cost management and governance.
- Assess the importance of aligning cloud costs with business outcomes.
- Consider the need for software license management.

# Top-Level Requirements for FinOps

## In Single and Multi-Cloud Environments
- Strategic Alignment and Governance
- Visibility and Reporting
- Cost Management and Optimization
- Operational Efficiency
- Culture and Change Management
- Security and Compliance
- Innovation and Scalability

# Forecasting of Budget and Costs

## Conclusion Validation

- Define annual budget for cloud costs
- Dissect annual budget into smaller slices like month and/or weeks
- Record actual costs on a fine grained detail like daily costs
- Create a forecast based on the actual costs
- Identify tradeoffs and need for actions like optimization

Goal is to not only record and forecast costs for the overall setup but on all parts - as fine grained as possible and aggregate them accordingly like clustering information for regions, subscriptions, resource groups, ...


Breaking down the annual budget and tracking costs allows for responsive financial management. This method supports:
- Granular Tracking
- Aggregation and Forecasting
- Delta Analysis
- Continuous Improvement
- Alignment with Business Goals

# Automatically Acting on Costs

## 1. Monitoring and Alerts
- **Azure and AWS Monitoring:** Both Azure Cost Management & Billing and AWS Cost Explorer allow you to monitor costs and set budget alerts. These services can notify you when you're approaching or have exceeded your budget.
- **Third-Party Tools:** Solutions like CloudHealth, Apptio Cloudability, and Flexera also provide advanced cost monitoring and alerting capabilities. These tools can be configured to send notifications based on specific cost-related conditions.

## 2. Automated Action Frameworks
- **Azure Automation and Logic Apps:** In Azure, you can use Azure Automation runbooks or Logic Apps triggered by cost alerts to automate actions. For instance, you could trigger a Logic App with a webhook from an Azure Budget alert to shut down or scale down resources.
- **AWS Lambda and CloudWatch:** In AWS, you can use a Lambda function triggered by CloudWatch alarms (set up for cost alerts) to automatically take actions like stopping EC2 instances or downscaling RDS instances.

## 3. Infrastructure as Code (IaC)
- **Terraform or Pulumi:** With IaC tools like Terraform or Pulumi, you can script your infrastructure to be more flexible. Although these tools don't directly interact with cost monitoring to trigger actions, you can use them in conjunction with CI/CD pipelines to apply changes based on alerts from monitoring tools.

## 4. Custom Solutions
- **API Integration:** Both Azure and AWS offer APIs for their cost management and billing services. You can write custom scripts or applications that use these APIs to monitor costs and then use cloud provider APIs to manage resources.
- **Combining Tools:** For example, use CloudHealth for detailed cost monitoring and alerts, and based on these alerts, trigger a script that uses cloud provider APIs or IaC tools to modify your infrastructure.

## Key Considerations
- **Granularity:** Determine the granularity of cost monitoring and actions. Decide if actions should be taken on a per-resource basis, per-service, or at the environment level.
- **Safety Measures:** Implement safety measures to avoid unintended disruptions. This could include confirmation steps before shutting down resources, especially in environments that might host critical development work.
- **Scheduling:** For predictable work patterns, consider scheduling resources to automatically shut down or scale down during off-hours, complementing this with cost-triggered actions for exceptions.

## Cloud Custodian in Cost Management and Governance

Cloud Custodian allows organizations to implement automated actions based on specific conditions, focusing on cost optimization, security, and governance across cloud environments. Its policy-driven approach provides a flexible framework for enforcing best practices and operational control.

### Features:
- **Multi-Cloud Support:** Works across AWS, Azure, and GCP, providing a unified tool for cloud governance.
- **Policy as Code:** Enables defining policies using simple YAML configurations, making it accessible for both developers and operations teams.
- **Cost Management:** Supports policies for identifying underutilized or expensive resources and can automate actions such as stopping or terminating instances, deleting unused volumes, or resizing resources to optimize costs.
- **Security and Compliance:** Automates compliance checks and remediation actions for security configurations, ensuring cloud environments meet organizational and regulatory standards.
- **Event-Driven Management:** Can react to real-time cloud events, enabling immediate actions based on resource changes or metrics.

### Use Cases for Cost Management:
- **Resource Optimization:** Automatically identify and take action on underutilized resources to reduce costs.
- **Budget Enforcement:** Trigger alerts or actions when spending exceeds predefined thresholds or budgets.
- **Cleanup and Maintenance:** Automatically remove unused resources, such as unattached volumes or obsolete snapshots, to avoid unnecessary charges.

### Getting Started:
1. **Install Cloud Custodian:** Available via pip or Docker, making it easy to integrate into existing workflows.
2. **Define Policies:** Write policies that specify the conditions under which actions should be taken, and what those actions should be.
3. **Deploy Policies:** Run Cloud Custodian with your policies against your cloud environment to enforce rules and automate actions.

### Example Policy for Azure VM Shutdown:
```yaml
policies:
  - name: azure-vm-shutdown-unused
    resource: azure.vm
    filters:
      - "tag:Environment": sandbox
      - type: value
        key: "CpuUsage"
        value_type: percentage
        op: less-than
        value: 10
    actions:
      - type: stop
```

# Next steps

## Tagging

- Use Azure policy to check that tags are correctly applied to all resources in Azure.
- Use Azure Cost Management tool to have an overview of costs related to tags.
- Use Azure Resource Graph to query all resources directly (Kusto Query Language).

```sql
Resources
| where isnull(tags['tag-name'])
```

## Analysis and Reporting

- Using PowerBI for deep dive analyitcs, forecasting and reporting
    - Exporting Azure Cost Management data into (e.g.) Azure Data Lake Storage (gen2) on a regular cadence (daily).
    - Connect PowerBI directly to the data storage of the exported cost data.
    - Possibly important other data sources like budget definitions in Excel.
    - Use Data Analysis Expressions (DAX) to create new columns to the data with aggregated and forecasted costs.
    - Use dashboards to visualize the costs analysis which are available for other stakeholders as well.

## Interactive analysis

- Use genAI to analyze and describe costs.
- By feeding the cost data into a genAI setup and to train a large language model with this data, users can interact directly with the data.
- Basically, a user can query the data with natural language and does not need to have the needed abilities to use PowerBI or other BI tools. 
- Additionally, the large language model can describe insights and findings in a natural language as well.

**Note:** There is an activity from MLE team to setup genAI. Feeding the costs and budget data into this setup would be straight forward and mutual beneficial.