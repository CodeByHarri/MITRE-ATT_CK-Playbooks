# Deobfuscate_Decode_Files_or_Information - T1140

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1140 |
| MITRE Sub-TTP | T1140 |
| Name | Deobfuscate/Decode Files or Information |
| Log Sources to Investigate | File monitoring logs for changes in specific directories often used for storage of decoded data. Antivirus logs for alerts related to suspicious file processing activities. Command-line activity logs to identify usage of utilities like certutil or copy /b for file manipulation. Endpoint detection and response (EDR) data for traces of potential malware decoding actions. |
| Key Indicators | Unexpected use of certutil with decode parameters or reading files with suspicious extensions (e.g., .exe, .dll) from unexpected directories. Command-line executions involving 'copy /b' operations that combine multiple files into a single binary. Detection of password prompts related to compressed files in areas of the file system not typically used for storage of such files. |
| Questions for Analysis | Was there a legitimate user requirement behind the deobfuscation activity? Does the file involved in the operation typically reside or execute from this location? Is there any other related suspicious activity originating from the same user account or endpoint device? |
| Decision for Escalation | Anomalous decoding or deobfuscation activities with no positive legitimate use case or explanation on file require escalation. If similar patterns of activity are detected across multiple users or endpoints, escalate as these could represent a broader campaign. |
| Additional Analysis Steps for L1 | Verify file origin and intended usage with the asset owner. Review recent modifications or permission changes on files involved in the observed activity. Cross-reference endpoint activity with reported intrusion artifacts or known threat indicators. Check whether antivirus logs show detection/cleaning of any related files around the activity timeframe. |
| T2 Analyst Actions | Conduct deeper forensic analysis on the endpoint, checking for additional malware components or persistence mechanisms. Correlate decoded files against threat intelligence databases to identify known malware signatures. Assess network logs for external connections made by the endpoint before or after deobfuscation activities. Verify whether unusual or unexpected processes resulted from potential user execution. |
| Containment and Further Analysis | Isolate the affected system(s) to prevent further compromise. Quarantine suspicious files or processes identified during analysis. Collect malware samples and any associated payloads for sandboxing and additional analysis. Engage with incident response teams to mitigate possible lateral movement or data exfiltration risks. |
