# Phishing_for_Information:_Spearphishing_Voice - T1598004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1598.004 |
| MITRE Sub-TTP | T1598.004 |
| Name | Phishing for Information: Spearphishing Voice |
| Log Sources to Investigate | Review call logs from VoIP systems, PBX systems, and telecommunication provider records. Monitor caller ID spoofing attempts and unusual call patterns such as calls from unknown or unexpected geographic locations. Analyze helpdesk or technical support ticket records for any reported vishing attempts. Evaluate email or instant messaging logs for communication that requests victims to call a particular number. |
| Key Indicators | Increased call volume to unknown numbers, reports from users about unsolicited calls requesting sensitive information, calls from numbers spoofed to appear as internal or trusted contacts, call recordings or transcriptions indicating social engineering tactics, and direct follow-up calls or messages asking for credentials or financial information. |
| Questions for Analysis | Have there been reports of suspicious phone calls from users? Are there patterns of calls from specific, unfamiliar numbers? Is the caller ID information consistent or does it show signs of spoofing? Were any urgent requests for sensitive information made during the call? |
| Decision for Escalation | Escalate to Tier 2 if multiple users report similar suspicious calls, if sensitive or proprietary information was divulged, or if there is evidence of a coordinated vishing campaign targeting the organization. |
| Additional Analysis Steps for L1 | Verify the legitimacy of callers by cross-referencing with known contact databases. Check for unusual calling patterns or geographic anomalies in call logs. Follow up with users who reported vishing attempts to gather additional details. |
| T2 Analyst Actions | Conduct deeper analysis of call records and communication patterns to identify the scale and scope of the vishing activity. Engage with telecommunication partners to trace call origins. Assess any potential data exposure or breaches. Notify potentially impacted individuals or departments. |
| Containment and Further Analysis | Implement measures to block known vishing numbers using telecommunication filtering tools. Educate employees about recognizing and reporting vishing attempts. Review and update internal communication protocols to prevent and mitigate future phishing attempts. Conduct a retrospective analysis post containment to improve detection and response strategies. |
