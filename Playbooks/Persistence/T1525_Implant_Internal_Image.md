# Implant_Internal_Image - T1525

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1525 |
| MITRE Sub-TTP | T1525 |
| Name | Implant Internal Image |
| Log Sources to Investigate | Focus on cloud provider logs, such as AWS CloudTrail, Google Cloud Audit Logs, and Azure Activity Logs. Additionally, investigate container registry logs (e.g., Docker Registry audit logs) and infrastructure orchestration tool logs, such as Terraform or CloudFormation logs. Example insights include image push/pull requests, creation of new images, and modifications to existing images. |
| Key Indicators | 1. Unusual modifications or new additions to cloud or container images in registry, especially outside of normal work hours.<br>2. Sudden changes in image versions without corresponding change management records.<br>3. Presence of unexpected or unauthorized executables within container images after analysis. |
| Questions for Analysis | 1. Has there been any unauthorized access to the container registry?<br>2. Are there any discrepancies between the expected and actual images being used in deployments?<br>3. Were there any recent privilege escalations or unusual access patterns to modify these images? 4. Have there been any alerts regarding web shell activity from within the infrastructure?  |
| Decision for Escalation | Escalate to Tier 2 if: 1. There are confirmed unauthorized modifications to images.<br>2. Unauthorized access by unfamiliar or new users to the registry is detected.<br>3. Detection of suspicious scripts or binaries inside the deployed container images. |
| Additional Analysis Steps for L1 | 1. Verify change management records for image modifications.<br>2. Cross-reference audit logs with known maintenance schedules.<br>3. Check if anomalous activities correlate with user account changes or breaches. 4. Retrieve a list of affected resources using the modified images. |
| T2 Analyst Actions | 1. Conduct a deeper forensic analysis of the modified images to identify malicious code or backdoors.<br>2. Validate findings of L1 by comparing image hashes with the last known good state.<br>3. Collaborate with DevOps to understand the context of changes and assess potential vulnerabilities. 4. Investigate related systems or services for compromise. |
| Containment and Further Analysis | 1. Isolate affected images by tagging them in the registry or moving them to a secure location.<br>2. Deploy previously verified safe images if possible.<br>3. Block further unauthorized access by adjusting permissions or network rules. 4. Implement monitoring and alerting on key image modifications. 5. Conduct a full security audit of image creation and distribution processes to identify weaknesses or gaps. |
