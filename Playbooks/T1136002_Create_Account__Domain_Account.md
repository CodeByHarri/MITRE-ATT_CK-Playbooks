# Create_Account:_Domain_Account - T1136002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1136.002 |
| MITRE Sub-TTP | T1136.002 |
| Name | Create Account: Domain Account |
| Log Sources to Investigate | Analyze Active Directory logs, specifically the 'Security' event log for Event IDs 4720 (A user account was created), 4732 (A member was added to a security-enabled global group), and 4728 (A member was added to a security-enabled local group). Check for logs from SIEM systems correlating AD events. Investigate any relevant logs from Identity and Access Management solutions that may capture account creation activities. |
| Key Indicators | Unusual domain account creation logs, particularly from non-admin hosts or using non-administrative accounts. Look for unexpected use of the 'net user /add /domain' command during off-hours or from anomalous locations/IPs. Sudden addition of a user to privileged groups (e.g., Domain Admins). |
| Questions for Analysis | Was the new domain account creation during normal business hours? Does the associated user account show legitimate administrative activity historically? Is there any corresponding ticket or change request for this account creation? Were there multiple accounts created in a small timeframe? |
| Decision for Escalation | Escalate if account creation occurred outside of prescribed change management windows, lacks documentation, belongs to sensitive groups, or was done from a non-standard location or workstation. If any actions occur against a critical infrastructure environment, elevate immediately. |
| Additional Analysis Steps for L1 | Verify the source of the account creation by checking recent user activity logs and any remote session activities. Validate if any approved change requests correlate with the account creation. Check for any abnormal behavior associated with the IP address or hostname involved. |
| T2 Analyst Actions | Perform deeper inspection into related endpoint forensic data to identify whether any unusual scripts or tools were executed. Examine network traffic for anomalies during and after the account creation event. Correlate this event with recent vulnerabilities or threat intelligence feeds for potential IoCs. |
| Containment and Further Analysis | Disable the suspicious domain account and remove it from all groups it was added to. Conduct a full security audit of all domain accounts recently created. Use EDR solutions to track processes and connections from systems where the account was created. If unauthorized activity is detected, initiate hunting procedures across the domain for other potential compromise indicators and prepare an incident response plan. |
