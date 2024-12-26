# Supply_Chain_Compromise:_Compromise_Software_Supply_Chain - T1195002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Initial Access |
| MITRE TTP | T1195.002 |
| MITRE Sub-TTP | T1195.002 |
| Name | Supply Chain Compromise: Compromise Software Supply Chain |
| Log Sources to Investigate | ['Software deployment logs from deployment systems like SCCM or Jenkins', 'Code repository logs from systems such as GitHub or Bitbucket', 'Network logs to track movement of software binaries', 'Application and OS logs on endpoints receiving the software', 'Vendor update server logs to detect unauthorized modifications'] |
| Key Indicators | ['Unexpected changes in application checksum/hash on endpoints', 'Modification timestamps on deployment scripts that do not match expected update schedule', 'Unauthorized access or changes to code repositories', 'Anomalous network activity during software updates, such as unusual IP addresses', 'Presence of non-standard or modified libraries in application directories'] |
| Questions for Analysis | ['Were there any unexpected deployments of software or updates? If so, what was the source?', 'Are the application binaries from the update matching the known good hash from the vendor?', 'Has there been any unauthorized access to the deployment or build environments?', 'Are there any users with elevated permissions that shouldn’t have them?', 'Are there any notable discrepancies in the update logs that correlate with known organizational threats?'] |
| Decision for Escalation | ['Escalate if unauthorized alterations are detected in any aspect of the software delivery pipeline.', 'Escalate if the source of software updates cannot be verified or if updates are from unknown or suspicious URLs.', 'Escalate if unusual access patterns or privilege escalations are observed in repository or update servers.'] |
| Additional Analysis Steps for L1 | ['Verify hashes of application binaries against known good baselines.', 'Review recent commits and changes in relevant code repositories for unauthorized changes.', 'Cross-reference user access logs with the list of personnel authorized to make changes to software.'] |
| T2 Analyst Actions | ['Perform an in-depth analysis of the network traffic during the software update periods to detect anomalies.', 'Correlate any suspicious changes with known threat actor TTPs for attribution.', 'Engage with developers or software distribution teams to validate update processes and timelines.'] |
| Containment and Further Analysis | ['Isolate affected systems from the network to prevent spread.', 'Initiate a rollback process using verified clean software versions.', 'Collaborate with vendor to confirm the integrity of the distribution channel.', 'Undertake a forensic investigation to determine the extent of the compromise and identify its entry point.'] |
