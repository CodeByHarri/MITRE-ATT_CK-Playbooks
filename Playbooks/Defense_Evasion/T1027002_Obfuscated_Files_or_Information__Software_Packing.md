# Obfuscated_Files_or_Information:_Software_Packing - T1027002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1027.002 |
| MITRE Sub-TTP | T1027.002 |
| Name | Obfuscated Files or Information: Software Packing |
| Log Sources to Investigate | Monitor logs from endpoint protection solutions and EDRs that can detect file modifications or newly created executables. Windows Event Logs, specifically Security and Application logs, should be examined for unusual processes starting or loading suspicious modules. Network traffic logs can also provide insight into potential C2 communications triggered by packed executables. Example log sources include Sysmon, process creation logs, and file integrity monitoring systems. |
| Key Indicators | Detection of new or rarely seen executables on the system, especially those that resemble common software but have unusual file sizes, signatures, or names. Identifiers include high entropy in binary files, absence of typical file metadata, and executable files with unique attributes (e.g., no version info). Any file attempting to communicate over a network shortly after execution is also a key indicator. |
| Questions for Analysis | Is the detected file a known application, or is it new or anonymous? Is the executable significantly different from previous versions? Does the suspected application communicate with known or unusual network regions? Are there other behavioral markers, such as CPU or memory spikes, following execution? |
| Decision for Escalation | Escalate to Tier 2 if the packed executable is not whitelisted and evidence suggests it is attempting network communications. Further escalate if there are multiple occurrences across different systems within a short timeframe or if any data exfiltration attempts are detected. |
| Additional Analysis Steps for L1 | Validate file hashes against known databases and check against any whitelists. Use tools like VirusTotal for reputation-based checks. Ensure pattern matching and anomaly detection logs are up to date. Flag discrepancies in executable paths and context. |
| T2 Analyst Actions | Conduct deeper binary analysis utilizing reverse engineering to unpack and inspect the executable. Utilize sandbox environments to safely run and analyze the behavior of the packed software. Examine network traffic patterns for exfiltration activities. Apply machine learning models to detect anomalies in large datasets. |
| Containment and Further Analysis | Isolate the affected system from network access to prevent further spread of the potential threat. Use digital forensics tools to obtain a copy of the packed executable for further in-depth analysis. Once reviewed, update the threat intelligence database with any new indicators of compromise found. Coordinate with incident response teams to assess the scope of the compromise and take appropriate remediation steps. |
