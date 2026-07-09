# 🤖 AI Employee Onboarding Automation

Automated end-to-end employee onboarding system built with n8n.

## 🚀 What it does
- Auto-sends personalized welcome email (Groq AI)
- Creates Google Calendar orientation invite
- Creates employee profile in Notion
- Sends Slack notification to HR team
- Emails manager with action checklist
- Creates department-specific tasks in Notion

## 🛠️ Tech Stack
- n8n (automation)
- Groq LLaMA3 (AI email generation)
- Google Forms + Sheets (data collection)
- Gmail (email automation)
- Google Calendar (scheduling)
- Notion (employee directory + tasks)
- Slack (HR notifications)
- Google Apps Script (webhook trigger)

## 📸 Screenshots
[Add screenshots here]

## ⚡ Workflow
Google Form → Webhook → Calendar → Notion → Slack → Manager Email → AI Email → Gmail

## 🔧 Setup
1. Import `workflow.json` into n8n
2. Configure credentials (Gmail, Notion, Slack, Groq)
3. Setup Google Apps Script webhook
4. Activate workflow
