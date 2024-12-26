# Obtain_Capabilities:_Vulnerabilities - T1588006

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1588.006 |
| MITRE Sub-TTP | T1588.006 |
| Name | Obtain Capabilities: Vulnerabilities |
| Log Sources to Investigate | Monitor web traffic logs, especially those related to known vulnerability databases like the National Vulnerability Database (NVD), public and private vulnerability disclosure platforms, or sites associated with security research communities. Inspect network traffic for signs of unauthorized access attempts or downloads from these databases. Check endpoint protection and DLP logs for unusual files being accessed or transferred that may relate to known vulnerabilities. |
| Key Indicators | Frequent or unusual access patterns to vulnerability databases, especially by users or systems that do not typically access such resources. Accessing private or proprietary vulnerability information from insider threat detection systems. Attempts to query repositories using vulnerability keywords or CVE identifiers. |
| Questions for Analysis | Have any unusual accounts accessed the system or vulnerability databases? Is there a sudden spike in the volume of data being downloaded from known vulnerability sources? Are there any unusual times or patterns to these access attempts, such as outside regular business hours? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of unauthorized access to private vulnerability information sources, early indications of potential exfiltration, or if privileged accounts are involved in these actions. |
| Additional Analysis Steps for L1 | Validate access logs against known user roles and permissions to ensure access was legitimate. Search for any phishing indicators or recent credential compromises that could explain unauthorized access. Confirm if there are related alerts from IDS/IPS systems. |
| T2 Analyst Actions | Conduct a deeper investigation into any correlated alerts from intrusion detection systems, check historical behavior of involved accounts or systems for contextual analysis, and perform a risk assessment on the exposed vulnerabilities being targeted. |
| Containment and Further Analysis | If unauthorized access is confirmed, immediately lock affected accounts, consult with IT to revoke inappropriate access rights, and update data access policies. Conduct a post-incident review, analyzing adversary objectives and exploit attempts. Additionally, coordinate with vulnerability management teams to ensure patches or mitigations are prioritized for high-risk vulnerabilities. |
