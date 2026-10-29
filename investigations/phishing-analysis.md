# Phishing Email Investigation

**Platform:** TryHackMe — SOC Level 1

**Investigation Type:** Phishing Detection and Alert Triage

**Environment:** Simulated SOC training environment

## 1. Incident Overview

During a SOC training exercise, I investigated an email flagged as potentially malicious. The message impersonated Microsoft Support and attempted to create urgency around a significant Microsoft Teams pricing increase.

## 2. Initial Alert Details

| Field | Observation |
|---|---|
| Subject | Important Update: Microsoft Teams Pricing Increase |
| Displayed Sender | Microsoft Support |
| Email Authentication | SPF: Fail / DKIM: Fail |
| Attachment | REPORT.rar |
| Alert Type | Phishing — Post Delivery |

## 3. Investigation

During the investigation, I reviewed the email's content, sender information, authentication results, and attachment details.

**Key findings:**

- The message claimed a dramatic price increase to encourage immediate action.
- SPF and DKIM authentication checks failed, raising concerns about sender authenticity.
- The email contained a compressed attachment that warranted additional scrutiny.
- The message used urgency and an apparently trusted brand to encourage interaction.

## 4. Assessment and Response

The combination of suspicious messaging, failed email authentication, and an unexpected attachment supported treating the email as a potential phishing threat.

The simulated alert was escalated for further review in accordance with the training workflow.

## 5. Lessons Learned

This investigation reinforced the importance of:

- Reviewing multiple indicators before making an alert classification.
- Understanding SPF and DKIM when evaluating email authenticity.
- Recognizing social engineering techniques.
- Documenting findings clearly for another analyst.
- Following established escalation procedures.

## 6. Skills Practiced

Phishing Analysis | Email Security | Alert Triage | Threat Identification | Incident Documentation

---

*This investigation was conducted in a simulated TryHackMe environment for educational purposes.*
