# Email Header Analysis — Evidence
**Tool Used:** Google Admin Toolbox Messageheader (toolbox.googleapps.com/apps/messageheader)
**Tool Used:** MxToolbox Email Header Analyzer (mxtoolbox.com/EmailHeaders.aspx)
**Sample Analyzed:** Sample 1 — "Account Verification" Phishing Email

---

## Simulated Header Block (Illustrative)

```
Received: from mail.secure-account-verify[.]com (unverified [185.220.101.45])
    by mx.company.com with ESMTP id a1b2c3d4;
    Fri, 12 Jun 2026 09:14:22 +0000
From: "Security Team" <support@secure-account-verify[.]com>
Reply-To: noreply@secure-acc-verify-mail[.]com
To: user@company.com
Subject: Urgent: Your Account Will Be Locked
Date: Fri, 12 Jun 2026 09:14:20 +0000
Message-ID: <a1b2c3d4e5f6@secure-account-verify[.]com>
SPF: FAIL (sender IP 185.220.101.45 is not authorized to send for company.com)
DKIM: FAIL (no valid signature found)
DMARC: FAIL (policy: reject; action: rejected/flagged)
Content-Type: text/html; charset=UTF-8
```

---

## Header Analysis Findings

| Check | Result | What It Means |
|-------|--------|---------------|
| **SPF (Sender Policy Framework)** | ❌ FAIL | The sending mail server is not authorized to send mail on behalf of the claimed domain — a strong phishing indicator |
| **DKIM (DomainKeys Identified Mail)** | ❌ FAIL | No valid cryptographic signature — the email's authenticity cannot be verified |
| **DMARC (Domain-based Message Auth)** | ❌ FAIL | The domain's policy explicitly says to reject or flag unauthenticated mail like this one |
| **From / Reply-To mismatch** | ⚠️ MISMATCH | `From` shows one domain, `Reply-To` shows a slightly different lookalike domain — classic spoofing tactic |
| **Sending IP reputation** | ⚠️ SUSPICIOUS | IP address does not correspond to any known legitimate mail server for the claimed organization |
| **Message-ID domain** | ⚠️ MATCHES sender domain | Confirms the email originated from the suspicious domain, not a legitimate platform |

---

## How to Read These Results (Plain English)

**SPF, DKIM, and DMARC** are three email authentication checks that legitimate
companies set up so that receiving mail servers can verify "yes, this email
really came from us." When all three fail, it's one of the strongest
technical signals that an email is forged or spoofed.

**From / Reply-To mismatch** means that even if a victim notices the sender
name looks right, clicking "reply" would actually send their response to a
completely different, attacker-controlled address.

---

## Screenshot Evidence (Real Tool Output)

This exact header block was submitted to both tools and screenshotted as proof:

| Screenshot | Tool | Confirms |
|-----------|------|----------|
| `screenshots/01_google_messageheader_analysis.jpeg` | Google Messageheader | MessageId, From, To, Subject, relay hop (mail.secure-account-verify[.]com → mx.company.com via ESMTP) |
| `screenshots/02_mxtoolbox_relay_info.jpeg` | MxToolbox | Relay delay graph, hop from 185.220.101.45 to mx.company.com, blacklist check |
| `screenshots/03_mxtoolbox_spf_dkim_dmarc.jpeg` | MxToolbox | Full "Headers Found" table — confirms SPF/DKIM/DMARC all FAIL and the Reply-To mismatch |

Both tools independently returned identical SPF, DKIM, and DMARC results,
confirming the analysis is reproducible and not a one-off reading.

---

## Step-by-Step: How This Analysis Was Performed

1. Obtained the raw email header text from the sample email
2. Pasted the full header block into Google's Messageheader tool
   (`https://toolbox.googleapps.com/apps/messageheader/`)
3. Cross-verified results using MxToolbox Email Header Analyzer
   (`https://mxtoolbox.com/EmailHeaders.aspx`)
4. Reviewed the SPF / DKIM / DMARC authentication results returned by both tools
5. Manually compared the `From` and `Reply-To` domains for mismatches
6. Documented all findings in the table above

---

*This header is illustrative and was constructed to demonstrate the analysis
process using publicly documented phishing header patterns. No real
organization's mail infrastructure was accessed or tested.*
