# Incident 01 – Phishing Email with Malicious External Link

## Alert Source
TryHackMe SOC Simulator (Email Security & Firewall Alerts)

## Severity
Medium (Phishing) → High (Firewall)

---

## Alert Description
An inbound email containing a suspicious external link was detected and flagged as a potential phishing attempt. A subsequent firewall alert indicated that a user attempted to access the external URL, which was blocked due to being listed in threat intelligence feeds.

---

## Initial Assessment
The email impersonated Amazon delivery services and used urgency to prompt user action. The presence of a shortened external URL increased the likelihood of phishing. Correlation with firewall logs was required to determine whether the link was accessed and whether any security controls were triggered.

---

## Investigation Steps

1. **Email Analysis**
   - Reviewed sender address: `urgents@amazon.biz`
   - Identified brand impersonation (Amazon)
   - Observed urgency and action-required language
   - Confirmed presence of an external shortened URL (`bit.ly`)

2. **URL Analysis**
   - Extracted URL from email content
   - Analyzed the URL using the analyst VM URL/IP security check
   - URL was confirmed as **malicious**

3. **Firewall Log Correlation**
   - Identified a high-severity firewall alert related to the same URL
   - Confirmed outbound connection attempt was **blocked**
   - Destination IP and URL matched the phishing email link

---

## Findings
- The sender domain `amazon.biz` is not a legitimate Amazon domain.
- The email used social engineering techniques (urgency and delivery failure).
- The shortened URL redirected to a known malicious destination.
- Firewall controls successfully blocked the outbound connection, preventing compromise.

---

## Conclusion
**Classification:** True Positive (Phishing)

**Impact:**  
No endpoint compromise observed. The malicious connection attempt was successfully blocked by the firewall.

**Action Taken:**
- Phishing alert confirmed and closed as True Positive
- Malicious URL and IP remained blocked
- User exposure contained by network security controls

---

## Skills Demonstrated
- Phishing email analysis
- URL and IP threat intelligence validation
- Alert correlation (email + firewall)
- True positive classification
- SOC-standard incident documentation
