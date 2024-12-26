# Abuse_Elevation_Control_Mechanism:_TCC_Manipulation - T1548006

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1548.006 |
| MITRE Sub-TTP | T1548.006 |
| Name | Abuse Elevation Control Mechanism: TCC Manipulation |
| Log Sources to Investigate | Investigate macOS system logs focusing on 'tccd' service logs, which may show unexpected changes or access attempts to the TCC database. Inspect MDM logs if applicable, particularly if there are modifications to permissions. Monitor AppleScripts and application execution logs for suspicious behavior. Look into system configuration files and security-related logs to determine if System Integrity Protection (SIP) was disabled. |
| Key Indicators | Unexpected modifications to the TCC database files at '/Library/Application Support/com.apple.TCC/TCC.db'. Execution of normally trusted macOS apps (like Finder) with unusual patterns or scripts, such as unexpected AppleScript execution. Disabling SIP on macOS devices. Unapproved or new permissions granted to applications or scripts that previously did not have access. |
| Questions for Analysis | Did any trusted macOS app execute an unexpected script or process? Were there recent changes or modifications to the TCC database? Was SIP disabled recently? Are there any entries in the system logs indicating unusual application execution or access requests for sensitive resources? |
| Decision for Escalation | Escalate to Tier 2 if any trusted macOS application is identified executing unauthorized scripts. Also, escalate if there are suspicious or unauthorized modifications to the TCC database, or if SIP was found to be disabled without proper authorization. |
| Additional Analysis Steps for L1 | Correlate logs from various sources, like process execution and MDM logs, to find any connections between initially trusted apps and the suspect activity. Verify the integrity of the TCC database and confirm if the SIP status has changed. Check if other systems within the network are experiencing similar issues. |
| T2 Analyst Actions | Conduct a deeper investigation into the modifications of the TCC database, tracing back to the initial point of compromise. Validate the authenticity of unexpected scripts executed by trusted applications. Perform forensic analysis on suspicious binaries executed under the Finder process with inherited permissions. |
| Containment and Further Analysis | Restore the TCC database from a known good backup if tampering is confirmed. Re-enable SIP as part of remediation if it was disabled. Quarantine any identified malicious processes or binaries. Conduct a thorough review of user and network activity to identify additional compromise points and fortify defenses against reoccurrence. |
