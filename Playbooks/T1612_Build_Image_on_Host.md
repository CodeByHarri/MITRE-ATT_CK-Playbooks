# Build_Image_on_Host - T1612

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1612 |
| MITRE Sub-TTP | T1612 |
| Name | Build Image on Host |
| Log Sources to Investigate | Investigate Docker daemon logs for 'build' API requests to identify any remote build activity. Check network traffic logs for unusual outbound connections to C2 domains/IPs that may indicate download of malicious components. Review system logs for non-standard user accounts executing Docker commands. Audit access logs for Docker API, including timestamps, origin IPs, and user-agents to trace unauthorized access attempts. |
| Key Indicators | Unusual build requests to Docker API from external IP addresses. Presence of Dockerfile initiating from unexpected sources. Changes to local Docker images that are not part of standard operations. Unauthorized user accounts or services executing Docker commands. Network communications from the host to suspicious or untrusted domains indicating potential C2 activity. |
| Questions for Analysis | Is the Docker 'build' command being executed by a known and authorized user? Does the origin of the Dockerfile correspond to a legitimate internal source? Are there any corresponding download activities from known malicious IPs or domains? Are there any discrepancies in user account activity, such as user accounts executing Docker commands for the first time? |
| Decision for Escalation | Escalate to Tier 2 if there is evidence of unusual Docker API build requests from external sources, unauthorized account activity executing Docker commands, or network traffic suggesting communication with known C2 infrastructure. Additionally, escalate if L1 cannot verify the source and legitimacy of the Dockerfile used in the build process. |
| Additional Analysis Steps for L1 | Verify if Docker build requests are part of regular deployment activities by consulting change management records. Check the Dockerfile for any unfamiliar commands or references to external resources. Cross-reference IP address reputations from network logs to identify known malicious entities. |
| T2 Analyst Actions | Deep-dive analysis into the Dockerfile to identify embedded commands or scripts that are potentially malicious. Conduct forensic analysis on the built container image to detect presence of malware or unexpected files. Correlate Docker build activities with other concurrent suspicious activities in the environment, such as privilege escalations. |
| Containment and Further Analysis | Immediately block any suspicious IP addresses making unauthorized requests to the Docker API. Isolate systems exhibiting suspicious Docker build activities to prevent further malicious actions. Perform memory and disk analysis on compromised hosts to identify and remove malware. Engage in threat hunting to identify similar patterns across other systems in the network. |
