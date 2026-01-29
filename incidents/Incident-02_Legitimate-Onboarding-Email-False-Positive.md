# Incident 02 – Legitimate Onboarding Email (False Positive)

## Alert Source
TryHackMe SOC Simulator (Email Security Alert)

## Severity
Medium

---

## Alert Description
An inbound email containing an external link was flagged as potentially suspicious by automated email security controls.

---

## Initial Assessment
The alert was triggered due to the presence of an external link. Further investigation was required to determine whether the email represented a phishing attempt or legitimate business communication.

---

## Investigation Steps

1. Reviewed the sender email address and domain
2. Analyzed the email content and context
3. Validated the embedded URL
4. Checked for threat intelligence matches related to the sender and URL

---

## Findings
- The sender domain belongs to a legitimate internal HR onboarding service
- The embedded link directed to a trusted internal domain
- No malicious indicators or suspicious behavior were identified

---

## Conclusion
**Classification:** False Positive  

**Reasoning:**  
The alert was triggered by automated detection of an external link; however, investigation confirmed the email was legitimate business communication.

**Action Taken:**
- Alert closed as False Positive
- No remediation required

---

## Skills Demonstrated
- Phishing false-positive identification
- Email content and sender validation
- URL verification
- Risk-based alert triage
- SOC-standard documentation
