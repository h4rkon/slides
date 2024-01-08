# Platform Landing Zone
**Remarks:** The following technoogy choices have been given by Dachser.

| Topic | Purpose | Alternatives | Proposed by | Comment |
|-------|---------|--------------|-------------|---------|
| Crowdstrike | Virus scanner | | Dachser | |
| System Center Operations Manager (SCOM) | Cross-platform data center management system | | Dachser | |
| Cortex | Cybersecurity platform |  | Dachser |  |
| ExpreesRoute connection | Private connection between data center and cloud setup | VPN over Internet, ... | Dachser | High availability and high throughput |
| Azure Bastion | Bastion host pattern in landing zone concept |  | Dachser |  |
| Cisco Firewalls | Firewall solution | | Dachser | |
| f5 Load Balancer | Load balancer | | Dachser | |
| Azure Active Directory | Identity and Access Management Service | | Dachser | |
| Splunk | Monitoring and analyzing machine generated log data | | Dachser | |
| Ivanti | IT Service Management | | Dachser | |
| Veeam | Data protection and disaster recovery solution | | Dachser | |


# Development Process

| Topic | Purpose | Alternatives | Proposed by | Comment |
|-------|---------|--------------|-------------|---------|
| Terraform | Infrastructure as Code | Biceps, Ansible, Chef | EPAM | Best practice to code infrastructure setup for reproduction and verification. Biceps is a real alternative but bound to Azure (not an option due to vendor lock in). Ansible, Chef are more for server configuration on IaaS  environments and not highly suitable in cloud setups. Terraform is de facto standard and is not bound to cloud platform providers.|
| AzureDevOps     | Source control and CI/CD functionality          | GitHub, GitLab       | EPAM | Used to manage code in versions and branches plus the functionality to enable CI/CD pipelines with automated builds and testing. |


# Applications/Services

| Topic | Purpose | Alternatives | Proposed by | Comment |
|-------|---------|--------------|-------------|---------|
| Service Mesh in general     | Intra cluster communication          | Kubernetes native features, gradual adoption       | Best practice | Service mesh frameworks are delivering communication management and abstracts the possible complexity in Microservice to Microservice communication away (Intra-cluster). The use of a service mesh approach can addressed in a later stage regarding the increase of maturity in service orientation.|
| Istio     | Service Mesh          | Linkerd, Consul       | EPAM | Provides robust routing for intra-cluster communication.|