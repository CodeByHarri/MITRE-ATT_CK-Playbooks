# Hide_Artifacts:_Resource_Forking - T1564009

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1564.009 |
| MITRE Sub-TTP | T1564.009 |
| Name | Hide Artifacts: Resource Forking |
| Log Sources to Investigate | Investigate file system logs to identify any access, modification, or execution of resource fork content. Use logs from the following sources: <br>- macOS file system events logs to catch commands like 'ls -l@', 'xattr -l'.<br>- EDR logs for process creation with unexpected offsets in executable content.<br>- Application logs for any anomalies in resource manipulation or execution |
| Key Indicators | Key indicators include: <br>- Presence of files with extended attributes indicating resource fork usage. <br>- Unexpected or unauthorized access and modification timestamps aligning with resource fork manipulations. <br>- Unusual process execution from paths or files known to have resource forks. |
| Questions for Analysis | 1. Are there any changes in the resource forks that align with known user activity?<br>2. Is there any unexpected spike in resource fork manipulations compared to baseline?<br>3. Are there known legitimate applications that might use resource forks in this manner?<br>4. Were the resource modifications executed at odd hours or from unusual IP addresses? |
| Decision for Escalation | Escalate to Tier 2 if there are unusual or unauthorized modifications to resource forks that don't match known activity, especially if followed by an executable being launched. Also, escalate if resource fork activity is linked to suspicious network behavior or involves a high-value asset. |
| Additional Analysis Steps for L1 | 1. Verify the user accounts associated with the detected resource fork access for any anomalies.<br>2. Cross-check the file paths involved with restricted or sensitive directories.<br>3. Review endpoint protection logs for any signs of related alerts or blocks. |
| T2 Analyst Actions | 1. Perform a deeper dive into the timeline of activities involving the resource fork along with any related file access.<br>2. Extract and analyze the contents of involved resource forks for any malicious code or executables.<br>3. Use historical data to correlate if this is part of a larger pattern of attacks or a targeted campaign. |
| Containment and Further Analysis | 1. Quarantine the affected systems to prevent lateral movement until further investigation is complete.<br>2. If malicious executables are confirmed, remove them and consider using file integrity monitoring to ensure no re-introduction or hidden persistence mechanisms are active.<br>3. Conduct a full security audit of the affected systems, applying patches or updates as necessary, while monitoring for any further anomalous activities. |
