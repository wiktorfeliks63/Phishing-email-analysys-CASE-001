# PH-001 – Suspicious UPS Delivery Notification Analysis

**Project type:** Email Security / Phishing Analysis  
**Analysis method:** Static Email Analysis  
**Classification:** Suspicious – Likely Phishing / Spam  
**Date of sample:** 09 August 2025

## Overview

This project documents the static analysis of a suspicious email impersonating a UPS delivery notification.

The message uses a UPS-related sender display name and a parcel-delivery subject. However, the sender information, external links and actual message content contain several inconsistencies that raise security concerns.

The objective was to inspect the email structure, identify suspicious indicators and document the findings in a structured investigation report.

## Analysis Scope

The investigation covered:

- Email metadata and sender information
- `Received` headers and visible delivery path
- SPF, DKIM and DMARC-related header fields
- MIME structure and message content
- Embedded URLs and external image references
- Potential tracking mechanisms
- Indicators of suspicious activity

## Key Findings

| Finding | Description |
|---|---|
| Brand impersonation | The sender display name uses a UPS-related identity. |
| Sender mismatch | The visible sender and envelope sender use different domains. |
| Authentication concerns | DKIM verification reports `No`; SPF and DKIM alignment are reported as failed. |
| DMARC result | The supplied header reports `dmarc=pass`. |
| Suspicious URL | The HTML contains an external link hosted on `timcard25.airmiles.ca`. |
| Content mismatch | The UPS-themed subject conflicts with the FlyLady promotional content. |
| Possible tracking | The HTML contains a remote 1 × 1 pixel image. |

## Tools & Techniques

**Tools:**
- Text editor for inspecting the raw EML file
- Manual email header inspection

**Techniques:**
- Static analysis of email headers
- Sender and domain comparison
- Authentication-header interpretation
- MIME and HTML inspection
- URL and external-resource identification
- Indicator documentation and risk assessment

## Conclusion

The analyzed email was classified as **Suspicious – Likely Phishing / Spam**.

The strongest indicators were the mismatch between the UPS-themed sender identity and the actual promotional content, inconsistent sender domains and the presence of an unrelated external URL.

The analysis does not confirm malware delivery, credential theft or malicious activity by the external host. These conclusions would require further investigation.

## Safety & Limitations

This was a static analysis of a single EML sample.

- No links were opened.
- No remote content was downloaded.
- No attachments or executables were run.
- No sandbox analysis was performed.
- No independent DNS, WHOIS or reputation checks were conducted.
- SPF, DKIM and DMARC results were interpreted from the supplied headers only.

The original EML file is not included in this repository. Recipient information and unique tracking URL parameters have been excluded from the public report.

## Project Files

```text
PH-001/
├──PH-001_Investigation_Report.pdf
└── Paradys!Masz paczke, ktora nie została odebrana. - 'UPS'' (ddxvqfbyhyejmqyjutazcyoggznw@cerrajeriaocana.com) - 2025-08-09 1921.eml
└── README.md
```

## Disclaimer

This project was created for educational purposes as part of a personal cybersecurity portfolio. The analysis is limited to the supplied email sample and should not be treated as a complete incident investigation.
