# Office_Application_Startup:_Outlook_Forms - T1137003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1137.003 |
| MITRE Sub-TTP | T1137.003 |
| Name | Office Application Startup: Outlook Forms |
| Log Sources to Investigate | Monitor Microsoft Outlook application logs, particularly focusing on entries related to form usage or modifications. Exchange server logs should be analyzed for any unusual access patterns or modification actions on mailbox forms. Additionally, examine Windows Event Logs for any Application or System level anomalies during Outlook startup. Look at Office 365 audit logs if applicable, for unusual email activity or administrative actions regarding forms. |
| Key Indicators | Detection of custom Outlook forms created or modified. Unexpected Outlook startup behavior, such as crashes or delays. Unusual email activity related to the sending or receiving of forms. Presence of code execution tied to Outlook processes. Network traffic anomalies when Outlook is executing, particularly connections to external or suspicious IP addresses. |
| Questions for Analysis | Was the Outlook form in question recently modified, and if so, by whom? Has the user received any emails around the time of Outlook startup that include suspicious attachments or forms? Does the Outlook environment show evidence of unauthorized administrative actions? Are there any unexpected network connections initiated by Outlook after startup? Has this user’s mailbox been involved in other suspicious activities? |
| Decision for Escalation | Escalate to Tier 2 if: There is confirmation of unauthorized modification of Outlook forms, presence of suspicious code within Outlook processes, or if unexpected and potentially malicious emails are involved in the form activity. Unusual network activity directly associated with Outlook forms should also lead to escalation. |
| Additional Analysis Steps for L1 | Verify the source and legitimacy of recent Outlook form modifications. Check email logs for patterns related to the receipt or sending of specially crafted emails. Identify any additional users impacted by similar unexpected Outlook behavior. Correlate system and network logs to identify suspicious activities synchronous with Outlook form execution. |
| T2 Analyst Actions | Conduct deeper forensic investigations into the modified Outlook forms to determine the nature and origin of the code. Utilize endpoint monitoring tools to check recent process creation and registry changes related to Outlook. Investigate whether the affected machine(s) show evidence of broader compromise or lateral movement. Consult with IT to verify whether these form modifications were part of sanctioned changes. |
| Containment and Further Analysis | Quarantine the affected user account to prevent further malicious activity. Remove or rollback changes to the Outlook forms and block any identified harmful scripts. Monitor the system and network for signs of further compromise, and strengthen email filtering policies to detect similar threats. Conduct a root cause analysis to determine how the compromise occurred, and work on patching any existing vulnerabilities or improving email hygiene practices. |