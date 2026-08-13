# Day 7 — AI Client Onboarding System

End-to-end business automation: a client calls a Vapi voice agent, and the 
entire onboarding process — classification, database entry, and team 
notification — happens automatically.

## Architecture
Client → Vapi Voice Agent → n8n Webhook → AI Classification (AI Agent + 
OpenAI Chat Model) → Airtable + Notion + Slack

## Contents
- `workflow/` — exported n8n workflow JSON
- `vapi/` — Vapi assistant configuration (system prompt, function tool schema)
- `screenshots/` — Airtable, Notion, and Slack results from 3 test calls

## Priority Logic
| Budget (PKR) | Priority |
|---|---|
| ≥ 500,000 | HIGH |
| 200,000–499,999 | MEDIUM |
| < 200,000 | LOW |

## Test Results
| Client | Company | Budget | Priority | Result |
|---|---|---|---|---|
| Ali | ABC Restaurant | 600,000 | HIGH | ✅ |
| Sara | GreenLeaf Boutique | 300,000 | MEDIUM | ✅ |
| Fahad | Fahad's Auto Repair | 100,000 | LOW | ✅ |
