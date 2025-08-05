# phishing-email-analysis-task

Task Overview

This report is part of a cybersecurity internship task focused on identifying and analyzing phishing emails. The task involved reviewing a suspicious email, examining its contents and headers, and identifying phishing indicators.


Email Summary

Subject: Your Amazon Account is Locked – Immediate Action Required
  Sender: `alert@amaz0n-support.com` (spoofed address)
  Link:`https://amazon.verify-account-secure.com` (malicious)
  Attachment: `Amazon_Verification_Form.docm` (macro-enabled document)


Analysis Performed

Email Body Indicators

| Indicator             | Description                                                            |

| Spoofed Email Address | Looks like a legit Amazon email but uses `amaz0n` instead of `amazon`. |
| Suspicious URL        | URL mimics Amazon but redirects to an unknown domain.                  |
| Urgent Language       | Creates panic: "Immediate Action Required", 24-hour deadline.          |
| Malicious Attachment  | `.docm` file that can contain malware macros.                          |
| Generic Greeting      | Uses "Dear Customer" instead of a real name.                           |
| Grammar & Tone        | Slightly off, designed to trigger fear.                                |

Header Analysis

| Check     | Result          | Explanation                                              |

| SPF       | ❌ Fail          | Sending IP not authorized to send emails for the domain. |
| DKIM      | ❌ Fail          | Signature validation failed.                             |
| DMARC     | ❌ Fail          | Policy not followed.                                     |
| Origin IP | `185.244.25.92` | Not associated with Amazon, possibly a known spam IP.    |



Tools Used

MxToolbox Email Header Analyzer
Email client (for viewing full headers)
Browser (for URL inspection via hover)


Conclusion
This email is a classic phishing attempt designed to steal user credentials or spread malware. The report documents:

 Technical evidence (header failures)
 Social engineering tactics
 Malicious indicators (URL, file type, spoofed domain)

Do not click any links or download attachments from suspicious emails. Report them immediately.

Files included 
Phishing_email_task_ss.pdf – Contains screenshots of the phishing email and analysis highlights.
Report_sanika.pdf – Detailed phishing email analysis report authored by Sanika.
email_actual.txt – Raw text version of the phishing email's body content.
email_header.txt – Extracted email header used for technical analysis of spoofing and authentication.
README.md – Overview of the task, tools used, analysis summary, and conclusions.

## Extra Research Insight
While header analysis and sender verification are powerful technical defenses, phishing threats have evolved to bypass them through “zero-day phishing pages” and QR code phishing (quishing). Zero-day phishing URLs are freshly registered domains that avoid detection by email security systems because they haven’t yet been flagged or blacklisted. Similarly, attackers are increasingly embedding malicious QR codes in emails, which redirect users to credential-harvesting websites via mobile devices. These attacks evade traditional email link scanners since QR codes are image-based. Organizations must therefore implement real-time URL scanning, AI-based anomaly detection, and promote user awareness training to adapt to these emerging techniques.

## Phishing Interview Q&A Summary
Phishing is a form of cyberattack where attackers impersonate legitimate entities to trick users into revealing sensitive information or installing malicious software. A phishing email often contains several red flags, such as a spoofed sender address, generic greetings like “Dear Customer,” urgent language designed to provoke immediate action, and suspicious links or attachments. Email spoofing specifically refers to falsifying the "From" address to make the email appear to come from a trusted source. These emails are dangerous because they exploit human trust and can lead to identity theft, financial loss, or system compromise.

To determine whether an email is genuine, users should carefully inspect the sender’s domain, hover over links to verify destinations, and check for inconsistencies or grammatical errors. Technical tools like MxToolbox, Google Admin Toolbox, or HeaderAnalyser.com can help dissect the header to confirm if SPF, DKIM, and DMARC authentication checks pass. If an email appears suspicious, it should be reported to the organization's security team or email provider immediately—never clicked or downloaded. Attackers also heavily rely on social engineering, manipulating emotions such as fear or curiosity to coerce users into taking unsafe actions. Recognizing these tactics is crucial for building a security-aware culture.
