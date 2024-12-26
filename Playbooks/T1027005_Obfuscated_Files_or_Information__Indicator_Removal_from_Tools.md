# Obfuscated_Files_or_Information:_Indicator_Removal_from_Tools - T1027005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1027.005 |
| MITRE Sub-TTP | T1027.005 |
| Name | Obfuscated Files or Information: Indicator Removal from Tools |
| Log Sources to Investigate | File integrity monitoring logs, Antivirus logs, Endpoint detection and response (EDR) logs, Network traffic logs. Examples include alerts from antivirus systems notifying of a signature detection, EDR logs showing execution of suspicious file names or hashes, and network logs indicating repeated failed attempts to communicate with a known C2 server before and after a detection event. |
| Key Indicators | Unusual changes to previously detected files, antivirus alerts indicating signature-based detections followed by attempts without detections, file hash anomalies, and process names/naming conventions that have been altered but maintain similar behaviors and connections as previously detected threats. |
| Questions for Analysis | Has the file in question been previously flagged or quarantined by antivirus solutions? Are there changes in the file hash or metadata that indicate a removal or alteration of detected characteristics? Is there any unusual activity from the host where the file was detected prior to and after the detection event? |
| Decision for Escalation | Escalate if there are repeated modifications to files that bypass detection after previous flags, if network communications continue from hosts previously detected with suspicious activities, or if there is a high incidence of altered malware file signatures from a known staging point or with a known threat actor signature. |
| Additional Analysis Steps for L1 | Verify the history of flagged files in security logs, check the timeline of detection versus modification activities, and assess correlation logs from antivirus and EDR tools. Also, review user logs and behaviors associated with detected files for any anomalies. |
| T2 Analyst Actions | Perform a deeper forensic analysis of file changes and connect them to potential adversarial activities or threat actor TTPs. Investigate if similar file alterations have been reported across other systems or nodes in the network. Consult threat intelligence databases for similar past incident patterns. |
| Containment and Further Analysis | Isolate affected systems from the network to prevent further spread. Acquire and preserve relevant artifacts, complete a detailed file analysis and reverse engineering if necessary, to understand the changes made. Ensure all malicious indicators are updated in threat intelligence and signature databases to enhance future detections. |
