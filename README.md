# FUTURE_CS_02 — Phishing Detection & Awareness Report
### Prepared by: Angel Proshia F
### Future Interns | Cyber Security Track | Task 2 | June 2026

---

## Task Overview
A professional phishing email detection and awareness assessment, conducted
as part of the **Future Interns Cyber Security internship programme**. This
task simulates the work of a real security analyst — analyzing phishing
email samples, identifying indicators, classifying risk, and producing a
client-ready awareness report that any business could use to train employees.

--- 

## What Was Analyzed

| Field | Details |
|-------|---------|
| **Samples Analyzed** | 3 phishing email samples |
| **Sample Source** | 1 from the official task brief + 2 modeled on common real-world phishing patterns |
| **Classification System** | Safe / Suspicious / Phishing |
| **Result** | All 3 samples classified as **PHISHING** |
| **Total Indicators Found** | 18 across all samples |
| **Assessment Date** | June 2026 |
| **Prepared By** | Angel Proshia F |
| **Report ID** | FUTURE-CS-02-2026 |

> All domains referenced in this assessment are **defanged** (written with
> `[.]` instead of `.`) and are illustrative placeholders. No real company,
> live website, or real victim data is involved. No links were clicked and
> no attachments were opened during this assessment.

---

## Scope

### In Scope
- Analysis of phishing email content and structure
- Email header inspection (SPF / DKIM / DMARC checks)
- Sender domain verification
- URL / link destination inspection (hover-only, no clicking)
- Risk classification and awareness documentation

### Out of Scope
- Clicking any links or opening any attachments
- Visiting any live (potentially malicious) domains
- Replying to or interacting with any phishing sender
- Use of real organisational or personal data

---

## Tools Used

| Tool | Purpose |
|------|---------|
| **Google Admin Toolbox — Messageheader** | Parses raw email headers to check SPF, DKIM, DMARC authentication |
| **MxToolbox Email Header Analyzer** | Cross-verification of header authentication and routing path |
| **Browser Tools (hover inspection)** | Safely previewing link destinations without clicking |
| **Public Phishing Datasets (referenced for study)** | rf-peixoto/phishing_pot, autinerd/phishing-mail-examples — used only for understanding real-world phishing structure, not directly reproduced |

---

## Findings Summary

| Email | Title | Classification | Key Technique |
|-------|-------|----------------|---------------|
| EMAIL-01 | Account Verification Scam | 🔴 PHISHING | Urgency + fear-based account lockout threat |
| EMAIL-02 | Invoice / Billing Scam | 🔴 PHISHING | Business Email Compromise (BEC) targeting finance |
| EMAIL-03 | Fake IT Helpdesk Password Reset | 🔴 PHISHING | Spear-phishing impersonating internal IT |

---

## Key Evidence

### Email Header Authentication Results
| Check | Result | Meaning |
|-------|--------|---------|
| SPF | ❌ FAIL | Sending server not authorized for claimed domain |
| DKIM | ❌ FAIL | No valid cryptographic signature found |
| DMARC | ❌ FAIL | Domain policy flags message as unauthenticated |

### Common Indicators Across All 3 Samples
- Urgency / time-pressure language
- Generic greetings (no real recipient name)
- Sender domain unrelated to claimed organisation
- Suspicious call-to-action links
- Fear of consequence if no action taken

---

## Repository Structure

```
FUTURE_CS_02/
│
├── README.md                              ← This file
│
├── report/
│   └── Phishing_Detection_Awareness_Report_FUTURE_CS_02.pdf
│
├── evidence/
│   ├── phishing_email_samples.md          ← All 3 analyzed email samples
│   ├── email_header_analysis.md           ← SPF/DKIM/DMARC analysis details
│   └── url_domain_analysis.md             ← Domain & URL inspection findings
│
└── screenshots/
    └── README.md                          ← Screenshot capture guide
```

---

## Report

**[Download Full Report PDF](report/Phishing_Detection_Awareness_Report_FUTURE_CS_02.pdf)**

The PDF report includes:
- Cover page with summary badges (3 emails analyzed, 3 classified phishing, 18 indicators)
- Table of contents
- Executive summary
- Scope and methodology
- Risk classification guide (Safe / Suspicious / Phishing)
- Email header analysis (SPF / DKIM / DMARC)
- 3 detailed email breakdowns — content, indicators, plain-English explanation
- URL and domain inspection findings
- Prevention and awareness guidelines
- Do's and Don'ts checklist for employees
- Ethics and disclaimer statement

---

##  Ethics Statement

This assessment was conducted **solely for educational purposes** as part of
the Future Interns Cyber Security Task 2 programme.

- No links were clicked; no attachments were opened
- No live or real malicious infrastructure was contacted
- All domains are defanged and illustrative — not real, registered, or owned
- No real personal, financial, or organisational data used
- Public datasets referenced only for study, never copied or reproduced directly
- Full compliance with Future Interns Task 2 ethical guidelines

---

## Author

| Field | Details |
|-------|---------|
| **Name** | Angel Proshia F |
| **Programme** | Future Interns — Cyber Security Track |
| **Task** | Task 2 — Phishing Detection & Awareness Report |
| **Track Code** | CS |
| **Repository** | FUTURE_CS_02 |
| **Date** | June 2026 |

---

*This report is for educational purposes only. All email samples are either
sourced from the official task brief or modeled on publicly documented
phishing patterns for training purposes.*
