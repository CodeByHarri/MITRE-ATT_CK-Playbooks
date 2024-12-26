# Remote_Services:_Cloud_Services - T1021007

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Lateral Movement |
| MITRE TTP | T1021.007 |
| MITRE Sub-TTP | T1021.007 |
| Name | Remote Services: Cloud Services |
| Log Sources to Investigate | Investigate authentication logs from cloud services such as AWS CloudTrail, Azure Activity Logs, and Google Cloud's IAM logs. Check logs for user sign-ins, authentication methods, and IP addresses associated with login activities. Look for anomalies in the sign-in patterns and authentication mechanisms (e.g., use of Application Access Tokens). |
| Key Indicators | Unusual login times, logins from anomalous geolocations or IP addresses, use of cloud CLI tools (e.g., Connect-AZAccount, Connect-MgGraph, gcloud auth login) from unexpected locations or by unexpected users, sudden surge in access attempts or resource usage in cloud services, use of Application Access Tokens that are not typically used in the environment. |
| Questions for Analysis | Is the login from an expected IP address or geolocation for this user? Was the access at a time that aligns with the user's normal activity hours? Does the user account typically use the Application Access Token method for authentication? Are there any concurrent logins from different locations that could indicate account compromise? |
| Decision for Escalation | Escalate if the authentication is from an unknown IP address or geolocation, occurs during unusual hours, involves the use of Application Access Tokens that aren't standard for that user, or there are multiple failed login attempts followed by a successful one. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the account used to log in by checking its recent activity and correlating with user reports or expected activity. Review recent password changes, if any, and analyze the authentication methods used for any anomalies in behavior. |
| T2 Analyst Actions | Conduct a thorough analysis of network paths and correlate with other potential indicators of compromise (e.g., suspicious file accesses, data exfiltration attempts). Cross-reference the occurrence of this activity with threat intelligence for known malicious indicators. Verify the roles and permissions of the account used to ensure they haven't been incorrectly elevated. |
| Containment and Further Analysis | If determined malicious, disable the compromised accounts and remove any suspicious access tokens. Adjust Identity and Access Management (IAM) roles and permissions to restrict access, if necessary. Conduct a forensic review of the affected cloud environment, focusing on what resources were accessed. Implement enhanced monitoring for the compromised account and associated resources moving forward. |
