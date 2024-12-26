# Create_Account - T1136

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1136 |
| MITRE Sub-TTP | T1136 |
| Name | Create Account |
| Log Sources to Investigate | Investigate Windows Security Event Logs, especially events related to account creation such as Event ID 4720 (A user account was created). In Linux systems, review 'auth.log' or 'secure.log' for useradd or adduser actions. In cloud environments, check access management logs such as AWS CloudTrail, Azure Active Directory logs, or GCP Admin Activity logs for new user creation events. Ensure to include logs from Identity and Access Management (IAM) solutions. |
| Key Indicators | Unusual account creation activity, such as accounts created by non-administrative users, accounts with highly privileged roles, accounts with names mimicking legitimate users, or accounts created at odd hours. In cloud platforms, monitor for accounts granted access to critical resources or with broad permissions. |
| Questions for Analysis | Was the account creation performed by an unexpected or unauthorized user? Is there any evidence of this account being used to access other systems or sensitive data? Is the timing of the account creation suspicious? Was the account creation followed by unusual or unauthorized activity? |
| Decision for Escalation | Escalate if any account was created without proper authorization, appears to be leveraged for lateral movement or privilege escalation, or if associated activities indicate potential compromise such as abnormal login attempts or data access patterns. |
| Additional Analysis Steps for L1 | Correlate the timestamps of account creation with other security events like failed login attempts or privilege escalation activities. Verify whether the account creation corresponds with legitimate user requests or administrative tasks. Use threat intelligence to check if the naming convention or IP addresses involved in the account creation are known for malicious activities. |
| T2 Analyst Actions | Perform deeper investigation into the origin of the account creation event. Check for access patterns of the newly created account. Utilize EDR solutions to look for related malicious activities around the time of account creation. Engage with IT or system owners to validate if the account and its associated actions were expected. |
| Containment and Further Analysis | Disable any unauthorized accounts immediately. Conduct a full audit of privileges assigned to the account. Review system and network logs to identify other potentially compromised systems. Implement additional monitoring for account usage. Coordinate with cloud service providers if the incident involves cloud environments for additional logging and analysis. |
