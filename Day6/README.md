# AI Automation Internship — Day 6

## Overview
This folder documents Modules 1–4 of the internship task: Airtable fundamentals, multi-table data modeling, Airtable–n8n integration (CRUD), and end-to-end automation workflows using n8n, Airtable, Slack, and Gmail.

## Module 1: Airtable Fundamentals
- Created an Airtable account and explored bases, tables, fields, views, automations, and forms.
- Built the **MATalogics AI Operations Base**.
- Created a table with sample records, a filtered Grid View, and explored the Automations and Forms tabs.

## Module 2: Multi-Table Data Model
Created the following tables inside the MATalogics AI Operations Base:

| Table | Fields |
|---|---|
| Clients | Client ID, Name, Company, Email, Status |
| Projects | Project Name, Assigned To, Deadline, Status |
| Leads | Lead Name, Source, Contact Number, Interested Service |
| AI Agents | Agent Name, Type, Deployment Status, Last Updated |
| Interns | Intern Name, Department, Task Count, Performance Score |

## Module 3: Airtable + n8n Integration (CRUD)
Connected Airtable to n8n using a Personal Access Token (scopes: `data.records:read`, `data.records:write`, `schema.bases:read`), then built and tested all four record operations:
- **Create Record**
- **Search Records**
- **Update Record**
- **Delete Record**

See [`Module 3 - Airtable complete.json`](./Module%203%20-%20Airtable%20complete.json) for the full n8n workflow (Create → Search → Update → Delete chained in sequence).

## Module 4: Automation Workflows
All four workflows (Lead Management, Client Onboarding, Project Tracking, and AI Agent Monitoring) are combined in [`Module 4_ Build Automation Workflows.json`](./Module%204_%20Build%20Automation%20Workflows.json).

| Workflow | Trigger | Action |
|---|---|---|
| Lead Management | New Lead in Airtable | Slack notification |
| Client Onboarding | New record created | Generate Client ID → Update Airtable → Slack notification |
| Project Tracking | Project Status changed | Email notification |
| AI Agent Monitoring | Agent Deployment Status changed | Slack notification to Ops |
## Key Troubleshooting
- Fixed a `403 Forbidden` error by adding the missing `schema.bases:read` scope and base access to the Airtable token.
- Discovered that Airtable Trigger data is nested under a `fields` object — expressions had to use `$json.fields['Field Name']` instead of `$json['Field Name']`.
- Fixed a Slack "No results" channel issue by switching the Channel selector to "By Name".
- Fixed an Airtable Update node that was matching records using a generated text ID instead of the real Airtable record ID.

## Screenshots
See the [`screenshots/`](./screenshots) folder for step-by-step screenshots of the Airtable base, n8n workflows, and Slack/email notification outputs.

## Status
All four modules completed and verified end-to-end.
