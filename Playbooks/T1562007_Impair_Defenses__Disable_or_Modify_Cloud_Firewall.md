# Impair_Defenses:_Disable_or_Modify_Cloud_Firewall - T1562007

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1562.007 |
| MITRE Sub-TTP | T1562.007 |
| Name | Impair Defenses: Disable or Modify Cloud Firewall |
| Log Sources to Investigate | Cloud provider logs such as AWS CloudTrail or Azure Activity Logs that capture changes in firewall rules or security groups. Monitor the creation, modification, or deletion of security group rules. Look into IAM activity logs for unusual access permissions or role escalations. Also, review network traffic logs for unexpected ingress/egress patterns on previously restricted ports/IPs. |
| Key Indicators | Creation or modification of security group rules allowing traffic from unknown or wide IP ranges. Increased ingress/egress network traffic on atypical ports and protocols. Unusual IAM activities like privilege escalations related to networking or firewall permissions. Alerts from intrusion detection systems indicating potentially malicious activities post-rule modification. Correlations with concurrent suspicious events like unusual resource utilization (e.g. CPU spikes due to cryptomining). |
| Questions for Analysis | Are there any recent changes to the cloud firewall rules or security groups? Who initiated these changes and do they align with expected activity or policy? What IP ranges and ports were affected by the changes? Have there been any corresponding alerts of unusual network traffic or activity subsequent to these changes? |
| Decision for Escalation | Escalate to Tier 2 if there are unauthorized changes to firewall rules or security groups that cannot be attributed to known authorized activities. Escalate if there's evidence of network traffic from unfamiliar IPs post-modification or concurrent unusual resource usage. |
| Additional Analysis Steps for L1 | Verify the identity of the user who modified the firewall settings and confirm if they had the authorization to make such changes. Review recent security group changes log for the scope and nature of modifications. Check for correlations with other alerts or incidents in the same timeframe. |
| T2 Analyst Actions | Perform a deeper investigation into the timeline of changes and correlate with IAM access patterns or potential exploitation vectors. Conduct forensic analysis on affected instances to determine if there was any compromise or payload delivery. Validate the necessity of firewall rule changes and verify against standard operating procedures. |
| Containment and Further Analysis | Revert unauthorized firewall changes immediately to the last known good configuration. Validate IAM roles and permissions for abuse of rights and remove any unauthorized access. Implement additional monitoring on sensitive resources and re-assess security group configurations. Conduct a post-incident review to find gaps in detection/prevention response and apply lessons learned to improve defenses. |
