# Incident 03 – Microsoft Credential Phishing (Allowed Connection)

## Alert Source
TryHackMe SOC Simulator (Email Security, Network Logs, Splunk)

## Severity
High

---

## Alert Description
An inbound email impersonating Microsoft Account Security was detected, claiming unusual sign-in activity and prompting the user to review account activity via an embedded link.

---

## Initial Assessment
The email exhibited multiple phishing indicators, including a look-alike sender domain and urgency-based messaging. Due to the credential-harvesting theme, further investigation was required to determine user exposure and network impact.

---

## Investigation Steps

1. **Email Analysis**
   - Reviewed sender address and identified typosquatting (`m1crosoft` instead of `microsoft`)
   - Confirmed impersonation of Microsoft Account Security
   - Identified embedded login link

2. **URL and Domain Analysis**
   - Analyzed the embedded URL
   - Domain confirmed malicious through threat intelligence checks
   - URL designed to mimic a Microsoft login page

3. **Network Log Review**
   - Reviewed Splunk logs for outbound traffic
   - Confirmed the connection to the malicious domain was **allowed**
   - Identified associated malicious IP address

---

## Findings
- The sender domain used character substitution to impersonate Microsoft.
- The embedded login URL was confirmed malicious.
- The outbound connection to the phishing infrastructure was allowed.
- User exposure to credential theft could not be ruled out.

---

## Conclusion
**Classification:** True Positive (Phishing)

**Impact:**  
Potential credential exposure. No immediate evidence of account compromise at the time of investigation; however, risk remained due to successful connection.

**Action Taken:**
- Escalated alert due to allowed connection and credential-harvesting risk
- Recommended password reset for the affected user
- Recommended review of authentication logs for suspicious activity
- Blocked the malicious domain and IP address

---

## Skills Demonstrated
- Credential phishing detection
- Typosquatting domain analysis
- SIEM log investigation (Splunk)
- Risk-based escalation
- Incident documentation and reporting
