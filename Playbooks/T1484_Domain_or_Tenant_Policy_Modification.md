# Domain_or_Tenant_Policy_Modification - T1484

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1484 |
| MITRE Sub-TTP | T1484 |
| Name | Domain or Tenant Policy Modification |
| Log Sources to Investigate | Investigate Active Directory logs, including changes to Group Policy Objects (GPOs) and domain trust settings. Azure Active Directory audit logs should be reviewed for changes in the configuration of identity tenants and federated identity providers. Specific examples include the Security Event logs, Azure AD Audit logs for tenant changes, and any logs from Identity Federation solutions. |
| Key Indicators | Detection of unusual modifications to GPOs, such as changes that deviate from normal patterns or are performed by unexpected users. Signs of newly added or modified trust relationships that include external domains or newly configured federated identity providers. Uncommon execution of rogue domain controller setup or deployment actions. |
| Questions for Analysis | 1. Have there been recent GPO changes that align with this activity?<br>2. Were any domain or tenant configurations altered without prior notification?<br>3. Are there unusual access patterns from users or accounts associated with domain policy changes? 4. Was any new federated identity provider added from outside your organization? |
| Decision for Escalation | Escalate to Tier 2 if there are unexplained modifications to domain or tenant policies, especially if new external domains are added to trust relationships or if federated identity providers are changed without authorization. |
| Additional Analysis Steps for L1 | Verify each policy change within the log sources against change request documentation. Check whether the user accounts involved have the appropriate rights for such changes. Note any discrepancies or lack of documentation for recent changes. |
| T2 Analyst Actions | Perform a deeper analysis of user activity who made the changes, looking for concurrent anomalies or typical malicious behaviors. Cross-reference changes with network traffic for related unusual patterns. Collaborate with IT for any unapproved changes to immediately revert the configurations. |
| Containment and Further Analysis | Revert unauthorized changes and increase monitoring of affected systems. Conduct a thorough review of user access rights and recent activities. Engage in vulnerability scanning to detect any consequent gaps due to modified settings. Schedule regular policy audits moving forward for better detection of such issues. |
