# 🤖 AI Employee Onboarding Automation

> Automated end-to-end employee onboarding system built with n8n, Groq AI, and Google Workspace — reducing manual HR effort to zero.

---

## 🔴 The Real Problem

Manual employee onboarding is broken in most companies:

- HR spends **3-5 hours per employee** on repetitive tasks
- New hires wait **days** for welcome emails, calendar invites, and system access
- Managers forget tasks — no workstation ready, no Slack access on Day 1
- No centralized tracking — HR doesn't know what's done and what's pending
- Human errors — wrong email sent, wrong department, wrong manager notified
- Multiple tools used manually — email, calendar, spreadsheet, all separate

**Result:** Poor first impression for new employees. High HR overhead. Missed tasks.

---

## ✅ How This Solves It

This system automates the **entire onboarding pipeline** in under 30 seconds:

```
HR fills Google Form
        ↓ (instant webhook trigger)
Google Calendar → orientation invite auto-created
        ↓
Notion → employee profile auto-created
        ↓
Notion → department-specific tasks auto-assigned to manager
        ↓
Slack → HR team notified instantly
        ↓
Gmail → manager gets action checklist
        ↓
Groq AI → personalized welcome email generated
        ↓
Gmail → employee receives warm welcome
```

**Zero manual work. Zero missed steps. Zero delay.**

---

## 🚀 What It Does

- **AI Welcome Email** — Groq LLaMA3 generates personalized welcome email with employee name, role, orientation time, manager details
- **Calendar Scheduling** — Auto-creates orientation event with dynamic time picked by HR
- **Employee Directory** — Notion profile auto-created with all employee details
- **Smart Task Assignment** — Department-specific onboarding tasks auto-created in Notion for manager
- **Instant HR Alert** — Slack notification to `#hr-onboarding` channel the moment form is submitted
- **Manager Briefing** — Automated email to manager with employee details and action checklist
- **Offer Letter Storage** — Google Drive link captured and stored in employee profile

---

## 🧠 Department-Specific Task Intelligence

System detects employee department and creates relevant tasks automatically:

| Department | Auto-Generated Tasks |
|---|---|
| Engineering | GitHub access, Dev environment setup, Code review guidelines |
| Design | Figma access, Design system, Brand guidelines |
| Product | PM tools, Product roadmap, Sprint introduction |
| Sales | CRM access, Sales playbook, Territory assignment |
| Marketing | Marketing tools, Brand guidelines, Campaign introduction |
| Operations | Ops tools, SOPs documentation, Workflow assignment |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **n8n** | Workflow automation orchestration |
| **Groq LLaMA3** | AI-powered personalized email generation |
| **Google Forms** | Employee data collection |
| **Google Sheets** | Form response storage |
| **Google Apps Script** | Instant webhook trigger on form submit |
| **Gmail** | Welcome email + manager alert |
| **Google Calendar** | Orientation scheduling |
| **Notion** | Employee directory + task management |
| **Slack** | Real-time HR team notifications |

---

## 📸 Screenshots

<img width="839" height="154" alt="image" src="https://github.com/user-attachments/assets/91a3dcca-1562-45f2-8a53-13717c740eef" />


---

## ⚡ Workflow Architecture

```
Google Form
    ↓
Google Apps Script (webhook trigger)
    ↓
n8n Webhook (instant trigger)
    ↓
Google Calendar (create orientation event)
    ↓
Notion (create employee profile)
    ↓
Slack (notify HR channel)
    ↓
Code Node (generate dept-specific tasks)
    ↓
Notion (create onboarding tasks for manager)
    ↓
Gmail (manager alert email)
    ↓
Groq AI (generate personalized welcome email)
    ↓
Gmail (send welcome email to employee)
```

---

## 🔧 Setup Guide

### Prerequisites
- n8n account (cloud or self-hosted)
- Google Workspace account
- Notion account
- Slack workspace
- Groq API key (free at groq.com)

### Steps

1. **Import workflow** — Import `workflow.json` into n8n

2. **Configure credentials** in n8n:
   - Google OAuth2 (Gmail + Calendar + Sheets + Drive)
   - Notion API key
   - Slack Bot token
   - Groq API key

3. **Create Google Form** with fields:
   - Full Legal Name, Personal Email, Phone, Date of Birth
   - Job Title, Department, Start Date, Orientation Time
   - Manager Name, Manager Email, Offer Letter upload

4. **Link Form to Google Sheet** — Responses tab → Sheets icon

5. **Setup Apps Script** — Extensions → Apps Script → paste `onFormSubmit` function → add trigger

6. **Create Notion databases**:
   - Employee Directory (Name, Email, Phone, Title, Department, Start Date, Status)
   - Onboarding Tasks (Task Name, Employee, Manager, Due Date, Status, Priority)

7. **Update Webhook URL** in Apps Script with n8n Production URL

8. **Activate workflow** in n8n → toggle Active ON

---

## ⚠️ Limitations & Drawbacks

- **No conflict detection** — Calendar events created without checking existing schedules
- **No duplicate prevention** — Same employee can be submitted twice if form resubmitted
- **Manual task completion** — Manager must update Notion task status manually
- **No error retry** — If one node fails, pipeline stops. No automatic retry built
- **Offer letter not parsed** — Stored as Drive link only; company name/salary not auto-extracted
- **English only** — Welcome email generated in English. No multilingual support
- **Slack free tier** — Message history limited to 90 days on free plan
- **No offboarding** — System handles onboarding only. Employee exit not automated
- **Google Forms dependency** — Only works with Google Forms trigger currently
- **Single timezone** — Calendar events use default timezone. No per-employee timezone support

---

## 🔮 Future Improvements

- [ ] Offer letter PDF parsing with GPT Vision to auto-extract company/salary details
- [ ] Conflict detection before calendar event creation
- [ ] Multi-language welcome email support (Gujarati, Hindi)
- [ ] Employee self-service portal to track onboarding progress
- [ ] Offboarding automation pipeline
- [ ] Duplicate submission detection
- [ ] Error handling and retry mechanism
- [ ] WhatsApp notification integration

---

## 👤 Author

**Vivek Solanki**
AI/ML Student — Charotar University of Science and Technology
[LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourprofile)# 🤖 AI Employee Onboarding Automation

> Automated end-to-end employee onboarding system built with n8n, Groq AI, and Google Workspace — reducing manual HR effort to zero.

---

## 🔴 The Real Problem

Manual employee onboarding is broken in most companies:

- HR spends **3-5 hours per employee** on repetitive tasks
- New hires wait **days** for welcome emails, calendar invites, and system access
- Managers forget tasks — no workstation ready, no Slack access on Day 1
- No centralized tracking — HR doesn't know what's done and what's pending
- Human errors — wrong email sent, wrong department, wrong manager notified
- Multiple tools used manually — email, calendar, spreadsheet, all separate

**Result:** Poor first impression for new employees. High HR overhead. Missed tasks.

---

## ✅ How This Solves It

This system automates the **entire onboarding pipeline** in under 30 seconds:

```
HR fills Google Form
        ↓ (instant webhook trigger)
Google Calendar → orientation invite auto-created
        ↓
Notion → employee profile auto-created
        ↓
Notion → department-specific tasks auto-assigned to manager
        ↓
Slack → HR team notified instantly
        ↓
Gmail → manager gets action checklist
        ↓
Groq AI → personalized welcome email generated
        ↓
Gmail → employee receives warm welcome
```

**Zero manual work. Zero missed steps. Zero delay.**

---

## 🚀 What It Does

- **AI Welcome Email** — Groq LLaMA3 generates personalized welcome email with employee name, role, orientation time, manager details
- **Calendar Scheduling** — Auto-creates orientation event with dynamic time picked by HR
- **Employee Directory** — Notion profile auto-created with all employee details
- **Smart Task Assignment** — Department-specific onboarding tasks auto-created in Notion for manager
- **Instant HR Alert** — Slack notification to `#hr-onboarding` channel the moment form is submitted
- **Manager Briefing** — Automated email to manager with employee details and action checklist
- **Offer Letter Storage** — Google Drive link captured and stored in employee profile

---

## 🧠 Department-Specific Task Intelligence

System detects employee department and creates relevant tasks automatically:

| Department | Auto-Generated Tasks |
|---|---|
| Engineering | GitHub access, Dev environment setup, Code review guidelines |
| Design | Figma access, Design system, Brand guidelines |
| Product | PM tools, Product roadmap, Sprint introduction |
| Sales | CRM access, Sales playbook, Territory assignment |
| Marketing | Marketing tools, Brand guidelines, Campaign introduction |
| Operations | Ops tools, SOPs documentation, Workflow assignment |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| **n8n** | Workflow automation orchestration |
| **Groq LLaMA3** | AI-powered personalized email generation |
| **Google Forms** | Employee data collection |
| **Google Sheets** | Form response storage |
| **Google Apps Script** | Instant webhook trigger on form submit |
| **Gmail** | Welcome email + manager alert |
| **Google Calendar** | Orientation scheduling |
| **Notion** | Employee directory + task management |
| **Slack** | Real-time HR team notifications |

---

## 📸 Screenshots

> Add workflow screenshots here

---

## ⚡ Workflow Architecture

```
Google Form
    ↓
Google Apps Script (webhook trigger)
    ↓
n8n Webhook (instant trigger)
    ↓
Google Calendar (create orientation event)
    ↓
Notion (create employee profile)
    ↓
Slack (notify HR channel)
    ↓
Code Node (generate dept-specific tasks)
    ↓
Notion (create onboarding tasks for manager)
    ↓
Gmail (manager alert email)
    ↓
Groq AI (generate personalized welcome email)
    ↓
Gmail (send welcome email to employee)
```

---

## 🔧 Setup Guide

### Prerequisites
- n8n account (cloud or self-hosted)
- Google Workspace account
- Notion account
- Slack workspace
- Groq API key (free at groq.com)

### Steps

1. **Import workflow** — Import `workflow.json` into n8n

2. **Configure credentials** in n8n:
   - Google OAuth2 (Gmail + Calendar + Sheets + Drive)
   - Notion API key
   - Slack Bot token
   - Groq API key

3. **Create Google Form** with fields:
   - Full Legal Name, Personal Email, Phone, Date of Birth
   - Job Title, Department, Start Date, Orientation Time
   - Manager Name, Manager Email, Offer Letter upload

4. **Link Form to Google Sheet** — Responses tab → Sheets icon

5. **Setup Apps Script** — Extensions → Apps Script → paste `onFormSubmit` function → add trigger

6. **Create Notion databases**:
   - Employee Directory (Name, Email, Phone, Title, Department, Start Date, Status)
   - Onboarding Tasks (Task Name, Employee, Manager, Due Date, Status, Priority)

7. **Update Webhook URL** in Apps Script with n8n Production URL

8. **Activate workflow** in n8n → toggle Active ON

---

## ⚠️ Limitations & Drawbacks

- **No conflict detection** — Calendar events created without checking existing schedules
- **No duplicate prevention** — Same employee can be submitted twice if form resubmitted
- **Manual task completion** — Manager must update Notion task status manually
- **No error retry** — If one node fails, pipeline stops. No automatic retry built
- **Offer letter not parsed** — Stored as Drive link only; company name/salary not auto-extracted
- **English only** — Welcome email generated in English. No multilingual support
- **Slack free tier** — Message history limited to 90 days on free plan
- **No offboarding** — System handles onboarding only. Employee exit not automated
- **Google Forms dependency** — Only works with Google Forms trigger currently
- **Single timezone** — Calendar events use default timezone. No per-employee timezone support

---

## 🔮 Future Improvements

- [ ] Offer letter PDF parsing with GPT Vision to auto-extract company/salary details
- [ ] Conflict detection before calendar event creation
- [ ] Multi-language welcome email support (Gujarati, Hindi)
- [ ] Employee self-service portal to track onboarding progress
- [ ] Offboarding automation pipeline
- [ ] Duplicate submission detection
- [ ] Error handling and retry mechanism
- [ ] WhatsApp notification integration

---

## 👤 Author

**Vivek Solanki**
AI/ML Student — Charotar University of Science and Technology
