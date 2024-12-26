# Process_Injection:_Asynchronous_Procedure_Call - T1055004

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1055.004 |
| MITRE Sub-TTP | T1055.004 |
| Name | Process Injection: Asynchronous Procedure Call |
| Log Sources to Investigate | To effectively investigate an incident involving APC injection, it's crucial to examine several log sources. These include:<br>1. **Windows Event Logs**: Specifically, Security Event Logs for suspicious process creation (Event ID 4688) and any process that creates handles with EVENT_WRITE (Event ID 4656).<br>2. **Process Monitoring Logs**: Logs that track process creation, termination, and changes in threads, which may include distinctions of injection activities.<br>3. **API Call Monitoring**: Integrate monitoring for calls to critical APIs such as `OpenThread`, `QueueUserAPC`, and other functions that may indicate injection attempts.<br>4. **Network Traffic Logs**: Analyze outbound connections from processes that have been identified as suspicious to detect any unauthorized data exfiltration attempts. |
| Key Indicators | Key indicators for APC injection include:<br>1. **Creation of Suspended Processes**: Abnormal process creation where the process is initially in a suspended state.<br>2. **Use of APC-related API Calls**: Detection of `QueueUserAPC`, `NtQueueApcThread`, and similar API calls associated with malicious process modification.<br>3. **Access to High-Integrity Processes**: Attempts to open handles to high-value target processes or those running with elevated privileges.<br>4. **Unusual Code Execution Context**: Execution of code in the context of a process where it is not normally expected, such as suspicious DLLs loaded via `LoadLibraryA`. |
| Questions for Analysis | 1. Is there evidence of APC-related API calls being used?<br>2. Did any process start off in a suspended state before executing unexpected code?<br>3. Are there any correlations between suspicious process injections and network activity or data leakage?<br>4. Can the accessed process and thread handles be justified by known applications or running tasks? |
| Decision for Escalation | Escalate to Tier 2 if: <br>1. There are confirmed instances of APC injection attempts, especially if associated with critical processes like those handling sensitive data or system operations.<br>2. The flagged behavior coincides with indicators of lateral movement or privilege escalation.<br>3. The victim process displays unexplained outbound network connections or anomalies in its normal behavior. |
| Additional Analysis Steps for L1 | For L1 analysis, further steps include:<br>1. Cross-reference suspicious processes with threat intelligence feeds for known signatures or behaviors.<br>2. Inspect the accessing application's parent lineage to determine if it was launched by a user or script.<br>3. Verify any anomalies with application or patch management records to rule out legitimate updates or new deployments as a root cause. |
| T2 Analyst Actions | Tier 2 analysts should:<br>1. Perform in-depth memory analysis of affected systems to identify hidden or stealthy code segments.<br>2. Use tools like Sysinternals or Volatility for forensic analysis on suspicious processes and threads.<br>3. Correlate logs across endpoints and network devices to identify broader attack patterns or campaign traces. |
| Containment and Further Analysis | 1. **Containment**: Immediately isolate the affected machine from the network to prevent further propagation.<br>2. **Kill/Quarantine**: Use endpoint security tools to terminate suspicious processes and quarantine files for further analysis.<br>3. **Forensic Analysis**: Capture memory dumps and disk images from the affected systems for a comprehensive forensic investigation. Analyze for any artifact consistency with known attack vectors.<br>4. **Network Monitoring**: Implement or enhance network monitoring around the incident time frame to detect potential lateral movements or exfiltration signals. |