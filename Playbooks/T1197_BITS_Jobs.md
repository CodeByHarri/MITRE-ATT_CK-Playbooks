# BITS_Jobs - T1197

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Persistence |
| MITRE TTP | T1197 |
| MITRE Sub-TTP | T1197 |
| Name | BITS Jobs |
| Log Sources to Investigate | Monitor Windows Event Logs, specifically Security and System logs for unusual BITS job creation and modification events. Collect and review PowerShell logs to identify BITS-related command execution, and utilize Sysmon logs to trace process creation related to BITS jobs. Endpoint Detection and Response (EDR) solutions can be used to detect anomalies or malicious patterns involving BITS. Monitor network logs to detect unexpected data transfers linked to BITS usage. |
| Key Indicators | Creation or modification of BITS jobs outside normal execution times, especially from non-standard users. Invocation of the BITSAdmin tool or PowerShell commands related to BITS jobs. Large or continuous data transfers via BITS that do not align with typical user or system behavior. Existence of long-standing BITS jobs set to execute scripts or executables upon completion. |
| Questions for Analysis | What user or process created the BITS job? Is there a legitimate need for the BITS job in question? Were any executable files or scripts specified as part of the BITS job? Has the user or system created similar BITS jobs in the past? Are there any accompanying events or logs indicating suspicious file transfers? |
| Decision for Escalation | Escalate if BITS jobs are created by unauthorized users or processes, if the job links to known malicious domains or IP addresses, or if there is an unexpected data transfer pattern involving the BITS service. Escalate if BITS jobs are configured to execute unexpected or unauthorized code. |
| Additional Analysis Steps for L1 | Correlate logs from different sources to confirm suspicious usage of BITS. Validate the necessity of BITS jobs by checking with system owners or reviewing change management records. Identify patterns of usage across other endpoints to determine if this is an isolated case or part of a widespread issue. |
| T2 Analyst Actions | Conduct deeper forensic analysis on affected systems to trace the origin of BITS-related activities. Check for associated network activity indicating command and control communication or data exfiltration. Examine the job contents in the BITS database for potentially malicious payloads. Review historical data for patterns that suggest wider compromise. |
| Containment and Further Analysis | Isolate the affected endpoint from the network if malicious BITS job activities are confirmed. Terminate suspicious BITS jobs and remove any unauthorized payloads. Update endpoint security policies to restrict unauthorized BITS job creation. Work with network teams to block communication with identified malicious IPs or domains. Perform a post-incident review to identify gaps in detection and response capabilities. |
