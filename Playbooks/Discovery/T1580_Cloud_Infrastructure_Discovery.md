# Cloud_Infrastructure_Discovery - T1580

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1580 |
| MITRE Sub-TTP | T1580 |
| Name | Cloud Infrastructure Discovery |
| Log Sources to Investigate | Focus on cloud provider logs such as AWS CloudTrail, Google Cloud's Stackdriver, and Azure Activity Logs. Look for logs related to API calls and CLI commands that involve actions like DescribeInstances, ListBuckets, HeadBucket, GetPublicAccessBlock, gcloud compute instances list, and az vm list. Correlate these logs with IAM user activity to identify access patterns. |
| Key Indicators | Unusual API calls for listing or describing cloud resources, especially from rare or unknown IP addresses. Anomalous use of compromised access keys for resource enumeration. Excessive accessibility changes or repeated access attempts to different resource types. |
| Questions for Analysis | Is there an unusual pattern or excessive calls to discovery APIs? Were these actions executed outside of normal business hours or from suspicious IP addresses or locations? Is there an unexpected use of service accounts or access keys that deviate from their typical behavior? |
| Decision for Escalation | Escalate if API calls or CLI commands were executed using compromised credentials, from an unauthorized IP address, or when a pattern of resource enumeration is observed that deviates from normal operational activities. |
| Additional Analysis Steps for L1 | Verify whether the activity corresponds to a legitimate administrative task. Check recent changes in access keys or IAM role assignments. Examine past activities of the user account involved for context. Look into any related alerts or incidents tied to the originating IP address. |
| T2 Analyst Actions | Conduct deeper analysis into the account or IP address performing the discovery activity. Check historical activity for patterns of enumeration or access attempts on various services. Verify the legitimacy of the accessed resources and investigate any associated data exfiltration attempts. |
| Containment and Further Analysis | If activity is deemed malicious, revoke or rotate compromised access keys immediately. Implement stricter access control policies and monitor subsequent API activity closely. Engage incident response procedures to determine the full scope of breach and prevent further unauthorized access. |
