# Phishing Email Samples — Analysis Evidence
**Collected/Modeled For:** Future Interns Cyber Security Task 2
**Note:** All samples below are either taken directly from the task brief or
modeled on common, publicly documented phishing patterns. All domains and IPs
are either defanged (using [.] notation) or replaced with safe placeholder
values to prevent accidental clicks or reproduction of live malicious
infrastructure. No real victim data is included.

---

## SAMPLE 1 — "Account Verification" Phishing (from Task Brief)

```
From: Security Team <support@secure-account-verify[.]com>
To: user@company.com
Subject: Urgent: Your Account Will Be Locked

Dear User,

We noticed suspicious activity on your account. To avoid account
suspension, please verify your details immediately.

Verify Now: http://secure-account-verify[.]com/login

Failure to verify within 24 hours will result in permanent account lock.

Regards,
Security Team
```

**Classification: PHISHING**

---

## SAMPLE 2 — "Invoice / Payment" Business Email Compromise (BEC) Style

```
From: Billing Department <accounts@invoice-billing-secure[.]net>
To: finance@company.com
Subject: Re: Outstanding Invoice #INV-88341 — Payment Overdue

Hi,

This is a follow-up regarding invoice #INV-88341 which remains unpaid.
Please find the attached invoice and process payment within 48 hours
to avoid late fees and service interruption.

Download Invoice: http://invoice-billing-secure[.]net/download?id=88341

If you have already paid, please disregard this message.

Best regards,
Billing Department
Accounts Receivable Team
```

**Classification: PHISHING**

**Why it's dangerous:** This style (Business Email Compromise) specifically
targets finance/accounts teams. It relies on urgency around money and
plausible business language rather than obvious scare tactics, making it
harder for employees to spot than Sample 1.

---

## SAMPLE 3 — "IT Helpdesk Password Reset" Spear-Phishing Style

```
From: IT Helpdesk <helpdesk@company-support-portal[.]com>
To: employee@company.com
Subject: Action Required: Password Expires Today

Hello,

Our records show your network password expires today at 5:00 PM.
To avoid being locked out of your email and company systems, please
reset your password using the secure link below.

Reset Password: http://company-support-portal[.]com/reset?user=employee

This link will expire in 2 hours for security reasons.

Thank you,
IT Helpdesk Team
```

**Classification: PHISHING**

**Why it's dangerous:** This impersonates an internal IT department —
a tactic called "spear phishing" because it targets employees within a
specific organization using familiar internal language ("network
password", "company systems") to appear legitimate.

---

## Common Pattern Observed Across All 3 Samples

| Pattern | Sample 1 | Sample 2 | Sample 3 |
|---------|----------|----------|----------|
| Urgency / time pressure | ✅ "24 hours" | ✅ "48 hours" | ✅ "2 hours" |
| Generic greeting | ✅ "Dear User" | ✅ "Hi," | ✅ "Hello," |
| Mismatched / suspicious sender domain | ✅ | ✅ | ✅ |
| Call-to-action link | ✅ | ✅ | ✅ |
| Consequence/fear if ignored | ✅ Account locked | ✅ Late fees | ✅ Locked out |
| Domain unrelated to claimed organization | ✅ | ✅ | ✅ |

---

*All sender domains shown above are illustrative/defanged examples and are
not live, registered, or owned domains used for malicious purposes by the
author of this report.*
