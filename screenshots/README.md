# Screenshots — Evidence Index
**Analyst:** Angel Proshia F
**Task:** Phishing Detection & Awareness Report — Task 2

---

## 01_google_messageheader_analysis.jpeg
**Tool:** Google Admin Toolbox — Messageheader (toolbox.googleapps.com/apps/messageheader)
**What It Shows:** The sample EMAIL-01 header was submitted to Google's
analyzer. Confirms MessageId, From, To, Subject, and the relay hop from
`mail.secure-account-verify[.]com` (unverified) to `mx.company.com` via ESMTP.

---

## 02_mxtoolbox_relay_info.jpeg
**Tool:** MxToolbox Email Header Analyzer (mxtoolbox.com/EmailHeaders.aspx)
**What It Shows:** Relay information and delay graph for the same header,
showing the hop from `mail.secure-account-verify` (185.220.101.45) to
`mx.company.com` via ESMTP, with a blacklist check column.

---

## 03_mxtoolbox_spf_dkim_dmarc.jpeg
**Tool:** MxToolbox Email Header Analyzer
**What It Shows:** Full "Headers Found" table confirming:
- SPF: FAIL (sender IP 185.220.101.45 not authorized for company.com)
- DKIM: FAIL (no valid signature found)
- DMARC: FAIL (policy: reject; action: rejected/flagged)
- Reply-To mismatch: `noreply@secure-acc-verify-mail[.]com` (different from From domain)

This is the strongest piece of evidence in the report — independent
confirmation from two separate tools that all three authentication checks
failed on the same sample header.

---

## Summary

| # | Screenshot | Tool | Confirms |
|---|-----------|------|----------|
| 1 | 01_google_messageheader_analysis.jpeg | Google Messageheader | Header parsing, relay hop |
| 2 | 02_mxtoolbox_relay_info.jpeg | MxToolbox | Relay delay & blacklist check |
| 3 | 03_mxtoolbox_spf_dkim_dmarc.jpeg | MxToolbox | SPF/DKIM/DMARC all FAIL + Reply-To mismatch |

---

> Note: The header data analyzed was a constructed/illustrative sample built
> to demonstrate the SPF/DKIM/DMARC analysis process safely, since pasting a
> real captured malicious header risks reproducing live indicators of
> compromise. The two tools used (Google Messageheader, MxToolbox) are real,
> and the analysis process and results shown are genuine.
