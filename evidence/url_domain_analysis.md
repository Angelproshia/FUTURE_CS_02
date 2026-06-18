# URL & Domain Inspection — Evidence
**Method:** Browser-based inspection (hover-preview, no clicking) + manual domain comparison
**Samples Analyzed:** All 3 phishing email samples

---

## Domain Comparison Table

| Sample | Claimed Organization | Actual Linked Domain | Legitimate Domain Would Be | Verdict |
|--------|----------------------|----------------------|----------------------------|---------|
| 1 | "Security Team" (generic) | secure-account-verify[.]com | N/A — no real company name given | ❌ Fake — invented domain designed to sound official |
| 2 | "Billing Department" | invoice-billing-secure[.]net | The actual vendor's real billing domain | ❌ Fake — generic finance-sounding domain not tied to any real vendor |
| 3 | "IT Helpdesk" | company-support-portal[.]com | Internal company domain (e.g. company.com) | ❌ Fake — external domain impersonating an internal department |

---

## Red Flags Identified in URLs

### 1. Lookalike / Invented Domains
None of the three links use the real, registered domain of the organization
they claim to represent. Instead, each uses a domain *invented to sound
official* — a common technique because registering a believable-sounding
domain is cheap and doesn't require impersonating an exact existing brand.

### 2. Generic Top-Level Domains (TLDs) Used to Appear Corporate
`.com` and `.net` were used in all samples, chosen specifically because they
appear default/legitimate to most users, unlike unusual TLDs that immediately
raise suspicion.

### 3. URL Structure Mimics Legitimate Login/Action Pages
All three links include path structures like `/login`, `/download?id=`, and
`/reset?user=` — designed to look like a normal, expected workflow (logging
in, downloading an invoice, resetting a password) so the destination feels
unremarkable.

### 4. No HTTPS / Padlock Verification Mentioned
None of the samples reference a secure HTTPS connection or display any
trust signal — a basic but often-overlooked indicator.

---

## Safe Inspection Method Used (No Links Were Clicked)

1. **Hover-only inspection** — In a real email client, hovering over a link
   (without clicking) reveals the actual destination URL in the status bar
   or a tooltip. This was used conceptually to compare the *displayed* link
   text against the *actual* destination.
2. **Domain defanging** — All domains in this report are written with `[.]`
   instead of `.` to prevent the links from being clickable or indexed as
   live URLs by accident.
3. **No browser navigation was performed** to any of the sample domains.
   This assessment is based on domain-name analysis and publicly documented
   phishing URL patterns, not live browsing.

---

## Quick Checklist Anyone Can Use

| Check | How To Do It |
|-------|-------------|
| Does the link domain match the company's real website? | Hover over the link, compare to the company's known URL |
| Is the domain spelled correctly? | Look for extra words, hyphens, or letter swaps (e.g. paypa1.com) |
| Is it asking you to log in, pay, or download something urgently? | Treat urgency + a link as an automatic red flag |
| Does the link use HTTPS? | Legitimate sites almost always use HTTPS — but note: phishing sites can too, so this alone isn't proof of safety |

---

*All domains referenced in this document are defanged and illustrative.
No live websites were visited during this assessment.*
