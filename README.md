
# Task 2: Analyze a Phishing Email Sample
**Internship:** Elevate Labs - Cyber Security Internship
**Tools:** Gmail ("Show original" for headers), MXToolbox Email Header Analyzer, screenshots
**Date:** 16-11-2026

## Objective
Identify phishing characteristics in a suspicious email sample and list the indicators found.

## What I Did
1. Took a real suspicious email from my Gmail **Spam** folder.
2. Examined the sender name and sender domain for spoofing or lookalike patterns.
3. Opened the full header (**Show original**), checked SPF, DKIM, DMARC and the Message-ID, and cross-checked it with the MXToolbox Email Header Analyzer.
4. Checked the subject and body for urgent, tempting or pressuring language.
5. Looked for attachments and spelling or grammar errors.
6. Summarised all indicators in `phishing_report.md`.

> Links were never clicked and no attachments were opened. Company names, my email address and the Message-ID are blurred in the screenshots.

## Key Findings
- SPF, DKIM and DMARC all **PASS**, so the email was not spoofed.
- Sent through a bulk email service (Amazon SES), with a list-unsubscribe header.
- Brand-like sender domain with a "-team" suffix.
- Clickbait salary subject, FOMO language and a paid-training sales push.
- Gmail classified it as spam.
- **Verdict:** unsolicited promotional spam that uses phishing-style tactics.

## Repository Contents
- `phishing_report.md` - full analysis report
- `01_spam_folder.png` - spam folder
- `02_email_body.png` - email body
- `03_header_analysis_blurred.png` - header authentication results (Gmail)
- `05.MxToolbox.Result.png` - header cross-check with MXToolbox

## Interview Questions

1. **What is phishing?**
   A fraud technique where attackers send messages that look like they come from a trusted source to steal credentials, money or data, or to install malware.
2. **How to identify a phishing email?**
   Check for a mismatched sender domain, urgent or threatening language, generic greetings, spelling errors, suspicious links (hover to see the real URL), unexpected attachments and failed SPF/DKIM/DMARC.
3. **What is email spoofing?**
   Forging the "From" address so the email appears to come from a trusted sender. It is possible because basic SMTP does not verify the From address; SPF, DKIM and DMARC help prevent it.
4. **Why are phishing emails dangerous?**
   They can lead to credential theft, malware or ransomware infection, financial fraud, business email compromise and data breaches.
5. **How can you verify the sender's authenticity?**
   Read the full header (SPF/DKIM/DMARC, Return-Path, Received chain), compare the domain with the official website, and confirm through an official channel.
6. **What tools can analyze email headers?**
   Gmail "Show original", MXToolbox Email Header Analyzer and Google Admin Toolbox Messageheader. VirusTotal can check suspicious URLs and attachments.
7. **What actions should be taken on suspected phishing emails?**
   Do not click or open anything, report it as phishing/spam, inform the IT or security team, and delete it. If a link was clicked, change passwords, enable MFA and scan the device.
8. **How do attackers use social engineering in phishing?**
   They use urgency, fear, authority, curiosity and rewards to push the victim to act quickly without thinking.

## Conclusion
Header authentication passing does not mean an email is safe. Combining header checks, sender-domain review and content analysis gives a much more reliable verdict.
