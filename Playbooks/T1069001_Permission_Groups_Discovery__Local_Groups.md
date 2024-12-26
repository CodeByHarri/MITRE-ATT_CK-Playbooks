# Permission_Groups_Discovery:_Local_Groups - T1069001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1069.001 |
| MITRE Sub-TTP | T1069.001 |
| Name | Permission Groups Discovery: Local Groups |
| Log Sources to Investigate | Monitor logs that capture command execution on endpoints. For Windows, check Security Event Logs (event ID 4688 for process creation) and Sysmon logs. For macOS, inspect Unified Logs and OpenBSM logs. For Linux, review syslog and auditd logs. It is important to identify the execution of commands 'net localgroup', 'dscl . -list /Groups', and 'groups'. Endpoint Detection and Response (EDR) solutions can also provide visibility into such activities. |
| Key Indicators | Unusual execution of 'net localgroup', 'dscl . -list /Groups', or 'groups' commands, especially by non-administrative users or executed from unexpected locations such as temporary directories. Look for anomalous process execution that deviates from normal user behavior or patterns outside of ordinary business hours. |
| Questions for Analysis | Which user account executed the command related to group discovery? Was the command executed from a known administrative tool location? Does the timing of the command align with normal user activity? Is there a history of this user account performing similar actions? |
| Decision for Escalation | Escalate if commands were executed by non-administrative users or service accounts not typically involved in such activities, particularly if this is associated with lateral movement or data collection. Escalate if there is evidence of subsequent suspicious behavior following group enumeration. |
| Additional Analysis Steps for L1 | Verify the context of command execution: check user access levels, the system from which commands were executed, and time of execution. Confirm the legitimacy with the system owner. Review historical login activity for the user account in question to check for anomalies. |
| T2 Analyst Actions | Conduct deeper analysis into the execution chain of the suspicious commands. Investigate any lateral movement or privilege escalation attempts that may correlate with group enumeration. Check for additional signs of compromise in memory or volatile data that relate to this discovery activity. |
| Containment and Further Analysis | If malicious activity is confirmed, isolate affected systems and disable compromised accounts. Consider resetting passwords for accounts exposed during group discovery. Perform a full audit of permissions and access controls. Review and reinforce group policy settings and monitoring capabilities to prevent future occurrences. |
