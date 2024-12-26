# Multi-Factor_Authentication_Interception - T1111

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1111 |
| MITRE Sub-TTP | T1111 |
| Name | Multi-Factor Authentication Interception |
| Log Sources to Investigate | 1. Authentication logs - Check for irregular login attempts or successful authentications from unusual locations or at unusual times.<br>2. System logs - Monitor for installation or execution of keyloggers, unusual network connections, or USB device insertion events when smart cards are used.<br>3. Network traffic logs - Look for suspicious outbound connections that could indicate data exfiltration or communication with command and control servers. 4. SMS gateway or email gateway logs - Review logs for interception or redirection of MFA codes. 5. Endpoint security logs - Monitor for suspicious processes or anomalies associated with known behaviors of keyloggers or other malware that might be used in conjunction with MFA interception. |
| Key Indicators | 1. Unexpected login attempts or authentications, especially those successful without prior failed attempts.<br>2. Discovery of keylogger or other malware that captures input from smart cards or other hardware tokens.<br>3. Unusual network traffic patterns linking to known malicious IP addresses or domains. 4. Evidence of SMS or email interception or anomalies in delivery paths for MFA codes. 5. Changes in configurations that disable or alter MFA protections on applications or services. |
| Questions for Analysis | 1. Are there login attempts from IP addresses or geolocations not typically associated with the user's activity?<br>2. Has there been any recent detection of malware that could capture or relay MFA data on the user's systems?<br>3. Are there any logs of failed authentication attempts before a successful login that might suggest brute-force or credential-stuffing attacks? 4. Is there evidence of interception or rerouting of MFA codes through SMS or email? 5. Does the observed behavior correlate with known indicators of compromise for keylogger or token interception threats? |
| Decision for Escalation | Escalate to Tier 2 if: 1. There is confirmed evidence of malware capable of MFA interception detected.<br>2. Authentication anomalies coincide with known threat actor techniques or indicators.<br>3. Log correlation shows a pattern consistent with active credential theft, such as replay attacks. 4. MFA code interceptions are observed without corresponding legitimate attempts from the user. 5. Unusual privileged access escalations post-authentication are logged. |
| Additional Analysis Steps for L1 | 1. Collect detailed logs around the time of suspicious authentication events.<br>2. Review historical access patterns for the user(s) involved to establish a baseline.<br>3. Verify the notifications and configurations for SMS/email services to ensure no settings were changed. 4. Examine network traffic logs for any correlations with known malicious sites or other indicators. 5. Validate the integrity of MFA systems to ensure they have not been tampered with. |
| T2 Analyst Actions | 1. Perform deeper analysis with threat intelligence to match observed indicators against known threats.<br>2. Execute endpoint detection and response (EDR) to identify any running keylogger or malware activities.<br>3. Collaborate with IT to conduct a forensic investigation on suspected endpoints. 4. Analyze network packets, especially encrypted traffic, for potential exfiltration markers. 5. Verify any patterns of failed or successful access to critical systems that may have gone unnoticed. |
| Containment and Further Analysis | 1. Isolate affected endpoints showing signs of keylogger installation or suspicious authentication.<br>2. Revoke and reissue MFA tokens or codes, ensuring the re-established process is secure.<br>3. Update firewall rules and threat intelligence feeds to block known suspicious IP addresses or domains. 4. Conduct a full audit of changes to MFA configurations and reinforce security policy adherence. 5. Engage with affected users to re-educate them on the importance of MFA and recognize phishing attempts. |