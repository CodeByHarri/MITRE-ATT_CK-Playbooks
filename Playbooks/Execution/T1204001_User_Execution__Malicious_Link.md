# User_Execution:_Malicious_Link - T1204001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1204.001 |
| MITRE Sub-TTP | T1204.001 |
| Name | User Execution: Malicious Link |
| Log Sources to Investigate | Examine web proxy logs for entries indicating access to known malicious domains or IP addresses. Review email gateway logs for evidence of inbound emails containing suspicious or known malicious links. Analyze DNS logs for unusual or unauthorized DNS requests to domains associated with phishing campaigns. Check endpoint protection logs for alerts related to execution of files or scripts downloaded after clicking a link. |
| Key Indicators | Unexpected web requests to suspicious or known malicious URLs. Emails containing links that are flagged by security filters. DNS queries for newly registered or uncommon domains. Execution of downloaded payloads on endpoint devices without typical user interaction or mismatch in filename extension and content type. |
| Questions for Analysis | Did the user receive any emails containing the suspicious link? Has this URL been accessed multiple times from different hosts in the network? Are there any alerts from endpoint protection solutions related to files downloaded from this domain? Does the domain have a history of malicious activity? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmation of access to a known malicious link, repeated access patterns across multiple hosts, or execution alerts following link interaction. Escalate if the accessed domain or IP is a well-documented phishing or malicious site. |
| Additional Analysis Steps for L1 | Correlate the timestamps of web proxy logs with email receipt timestamps to determine possible phishing attempts. Perform a reputation check on the domain or URL involved using threat intelligence platforms. Verify if the suspicious link results in any unauthorized file downloads or execution attempts on the user’s system. |
| T2 Analyst Actions | Deep dive into the reputation and behavior of the domain using threat intelligence tools. Analyze endpoint logs to identify any potential malware execution. Conduct a network traffic analysis to determine if any data exfiltration attempts associated with the malicious link were made. Review other users' activity logs to identify potential wider impact. |
| Containment and Further Analysis | Block malicious URL and domain at the gateway and proxy level to prevent further access. Quarantine any endpoints affected by execution of malicious payloads for further forensic investigation. Notify impacted users to raise awareness and conduct a security audit of affected systems. Capture and analyze network traffic samples to further assess the potential data exfiltration risks or wider compromise attempts. |
