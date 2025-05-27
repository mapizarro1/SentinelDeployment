
# 🛡️ Azure Sentinel Deployment Documentation

## 📌 Overview
This document describes the architecture, configuration, and integration details of the Azure Sentinel deployment for the FEDRamp environment.

## 🔧 1. Deployment Details

| Property | Value |
|----------|-------|
| Workspace Name | `example-law-eastus` |
| Sentinel Instance | Enabled in `Log Analytics` workspace |
| Resource Group | `rg-security-monitoring` |
| Region | `East US` |
| Deployment Method | Terraform / Bicep / Azure Portal / ARM |
| Owner(s) | Security Engineering Team |
| Date of Deployment | MM/DD/YYYY |

## 🧱 2. Components Deployed

- **Log Analytics Workspace**
- **Azure Sentinel (enabled on workspace)**
- **Data Connectors:**
  - Microsoft 365 Defender
  - Azure Activity Logs
  - Microsoft Defender for Cloud
  - Syslog / CEF (for on-prem or third-party sources)
- **Analytics Rules:**
  - Built-in + Custom KQL queries
- **Workbooks:**
  - [List workbooks used or customized]
- **Playbooks (SOAR):**
  - [Name], triggered by [Alert/Rule], performs [Action]
- **Watchlists:**
  - [If used – e.g., IP or user blocklists]

## 🔄 3. Automation & Integration

- **Playbooks Deployed via:** Logic Apps / Power Automate
- **Alert to Ticket Integration:** ServiceNow / Jira / Email
- **Automation Rules:** [List rules that triage alerts or trigger playbooks]

## 🔐 4. Access Control & RBAC

| Role | Scope | Assigned To |
|------|-------|-------------|
| `Microsoft Sentinel Contributor` | Resource Group | `sec-team@example.com` |
| `Reader` | Subscription | `compliance-team@example.com` |

## 📊 5. Monitoring & Health

- **Heartbeat configured for:**
  - Log sources (VMs, firewalls, etc.)
- **Alert latency baseline:** ~30–60 seconds
- **Watchdog alerts:** [e.g., “no data received from X source in 1 hour”]

## 🧪 6. Testing & Validation

| Test | Result | Notes |
|------|--------|-------|
| Alert trigger from M365 log | ✅ | Confirmed playbook executed |
| Syslog message from firewall | ✅ | Parsed by CEF connector |
| Sentinel rules firing as expected | ✅ | Baseline anomaly detection validated |

## 📁 7. Files & Repository Structure

```
/sentinel/
├── main.tf / sentinel.bicep
├── workbooks/
├── analytics_rules/
├── playbooks/
├── watchlists/
└── README.md
```

## 📘 8. Notes & Future Improvements

- Enable UEBA or Fusion detection?
- Integrate with Microsoft Purview?
- Improve alert tagging and classification logic.
