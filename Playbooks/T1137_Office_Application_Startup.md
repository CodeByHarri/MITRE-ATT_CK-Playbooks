# Office_Application_Startup - T1137

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1137 |
| MITRE Sub-TTP | T1137 |
| Name | Office Application Startup |
| Log Sources to Investigate | Investigate logs related to Microsoft Office applications, specifically: Office Application logs, Windows Event Logs, especially Application and Security logs, Office 365 activity logs, Exchange Server logs, and Outlook application logs. Examples include auditing for macro execution events, checking for recently installed add-ins, and reviewing any unusual Outlook rule modifications or home page configurations. |
| Key Indicators | Unusual background task activity associated with Outlook or Office at startup, recent installations or modifications of Office add-ins or templates, macros running without user initiation, modifications to Outlook rules that redirect or copy emails, and unauthorized changes to the home page of Outlook. |
| Questions for Analysis | Are there any unauthorized add-ins or templates recently installed? Were there any unexpected Outlook rules or home page modifications? Is there a pattern of macro execution that does not correspond with legitimate user activity? Have any suspicious or unusual email forwarding rules been created? |
| Decision for Escalation | Escalate to Tier 2 if there is any detection of anomalous installations of Office add-ins, unauthorized modification of Outlook rules/forms, or suspicious macro executions that cannot be explained through legitimate business needs. |
| Additional Analysis Steps for L1 | Verify the legitimacy of installed Office add-ins and templates by cross-referencing with approved software lists, check for unusual patterns in macro usage, review user email rules and identify any originating from unsecured or unverified sources, and confirm whether modifications to the Outlook home page were intentional. Look for any correlation with user support tickets or communications regarding unusual Office behavior. |
| T2 Analyst Actions | Conduct a deeper investigation into the timeline of add-in installations and macro executions, review user activity and historical logs to identify patterns or linkages to other suspicious activities, validate the origin and purpose of suspect email rules, and perform a threat intelligence lookup for any indicators of compromise related to the detected activities. |
| Containment and Further Analysis | If malicious activity is confirmed, disable and remove unauthorized add-ins, restore Outlook rule configurations to their original state, restrict affected accounts, and perform a detailed risk assessment. Notify affected users about potential changes made to their Outlook configurations. Conduct user awareness training to identify phishing and suspicious email activities, and ensure that Office applications are updated to mitigate exploitation of known vulnerabilities. |
