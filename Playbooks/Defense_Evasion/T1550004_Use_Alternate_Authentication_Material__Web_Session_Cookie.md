# Use_Alternate_Authentication_Material:_Web_Session_Cookie - T1550004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Lateral Movement |
| MITRE TTP | T1550.004 |
| MITRE Sub-TTP | T1550.004 |
| Name | Use Alternate Authentication Material: Web Session Cookie |
| Log Sources to Investigate | Web server logs, SIEM solution logs, application access logs, browser history logs, and cloud service provider logs (e.g., AWS CloudTrail, Azure Monitor) should be examined. Focus on logs that show session activity such as login times, IP addresses, user-agent strings, and session creation and termination events. |
| Key Indicators | Suspicious session IDs not associated with a recent user login event, access to web applications without accompanying authentication attempts, changes in IP addresses or user-agent strings during active sessions, multiple simultaneous logins from geographically disparate locations, and abnormal activity times that do not match the user's typical usage pattern. |
| Questions for Analysis | 1. Was there a successful login attempt prior to the suspicious activity?<br>2. Are there sudden changes in the IP address or user-agent string associated with the session?<br>3. Is the session being accessed from a location inconsistent with previous user behavior? 4. Does the session show activity that matches known malicious patterns or exceeds usual user actions? |
| Decision for Escalation | Escalate to Tier 2 if there are indicators of compromised sessions without corresponding user actions, repeated suspicious access attempts, or when accessing sensitive application components outside of normal patterns. If known IPs associated with previous attacks are detected or there are strong geographical discrepancies, escalation is warranted. |
| Additional Analysis Steps for L1 | Verify if the IP and user-agent changes relate to known benign activities. Review the specific application's access logs for unusual patterns that could reflect stolen session usage. Correlate the timing of the suspicious activities with the user's typical working hours. |
| T2 Analyst Actions | Conduct a deeper inspection of network traffic to the application during the suspicious session. Contact the user to verify if the activity was legitimate or if they noticed any issues. Analyze historical session data around the current anomaly to detect patterns. Review internal and external threat intelligence for related compromise techniques. |
| Containment and Further Analysis | Revoke potentially compromised session tokens and force re-authentication. Consider implementing stricter controls on session lifetimes and expanding logging to capture additional session attributes. Ensure MFA implementation is reviewed for potential weaknesses and initiate an incident response if necessary to mitigate unauthorized access risks. |
