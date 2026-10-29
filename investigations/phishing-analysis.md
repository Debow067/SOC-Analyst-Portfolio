# Phishing Email Investigation

**Platform:** TryHackMe — SOC Level 1  
**Investigation Type:** Phishing Detection and Alert Triage  
**Environment:** Hands-on cybersecurity training lab

## 1. Incident Overview

During a simulated SOC exercise, I reviewed an email flagged for possible phishing. The message appeared to come from Microsoft Support, claimed that Microsoft Teams pricing was increasing dramatically, and encouraged the recipient to open a report.

## 2. Evidence Available in the Lab

| Field | Observation |
|---|---|
| Subject | Important Update: Microsoft Teams Pricing Increase |
| Displayed Sender | Microsoft Support <support@microsoft.com> |
| Authentication Results | SPF: Fail / DKIM: Fail |
| Attachment | REPORT.rar |
| Alert Context | Phishing — Post Delivery |

These are details recorded from the training scenario, not findings from a live production email system.

## 3. Investigation and Analysis

| Indicator | Why it mattered | Limitation or alternative explanation |
|---|---|---|
| Urgent 600% price-increase claim | Unusual urgency can pressure recipients into opening links or attachments without verifying the message. | An unusual claim alone does not establish malicious intent. |
| Microsoft Support branding | A familiar name can make a fraudulent message appear legitimate. | The displayed sender can differ from the underlying sending infrastructure; the display name alone cannot verify identity. |
| SPF and DKIM failures | Failed authentication increases concern that the email may not have been authorized or may have been altered. | Forwarding, configuration issues, and other legitimate email-handling scenarios can cause failures. Results should be considered with headers, alignment, and broader context. |
| REPORT.rar attachment | An unexpected compressed attachment deserves closer inspection because it may conceal additional files. | The attachment name and archive format do not prove that its contents are malicious. |

### Assessment

The combination of a high-pressure message, failed authentication checks, brand impersonation indicators, and an unexpected archive supported treating the email as **suspected phishing** and escalating it for further review.

This assessment is based on the indicators available in the lab. I did not establish from these details alone that the attachment contained malware or that a recipient opened it.

## 4. Response and Escalation

In the simulated workflow, I escalated the suspicious email alert for further review. The key information for the receiving analyst was the email subject and sender, authentication failures, attachment name, and reasons for the phishing assessment.

**Additional checks that would strengthen a real-world investigation:**
- Review complete email headers, sender domains, and DMARC alignment.
- Inspect any links and attachment contents using approved, isolated analysis tools.
- Check delivery and user-interaction logs to determine whether the message was opened or the attachment executed.
- Look for similar messages sent to other recipients and follow the organization's incident response procedures.

These are recommended next steps, **not actions I claim to have completed in this lab**.

## 5. Lessons Learned

- Evaluate several indicators together instead of relying on one suspicious detail.
- Distinguish observed evidence from assumptions and unverified conclusions.
- Recognize how sender spoofing and urgency can support phishing attempts.
- Document reasoning so the next analyst understands the escalation decision.
- Be precise about what investigation steps were actually performed.

## 6. Skills Practiced

Phishing Analysis | Email Security | Alert Triage | Threat Identification | Incident Documentation
