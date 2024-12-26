# Inter-Process_Communication:_Dynamic_Data_Exchange - T1559002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1559.002 |
| MITRE Sub-TTP | T1559.002 |
| Name | Inter-Process Communication: Dynamic Data Exchange |
| Log Sources to Investigate | Monitor application logs, especially Microsoft Office applications for abnormal process creation events. Use event logs to look for registry changes that may enable DDE. Network logs should be assessed for unexpected data transfers or connections often associated with phishing campaigns. Example logs include Sysmon Event ID 1 (process creation), Windows Security Event ID 4688 (a new process has been created), and Registry changes captured by Sysmon Event ID 13. |
| Key Indicators | Presence of documents or spreadsheets with suspicious DDE payloads often discovered in email attachments or from untrusted external sources. Detection of registry modifications enabling DDE. Process execution from Microsoft Office applications, such as instances of winword.exe or excel.exe spawning cmd.exe or powershell.exe. |
| Questions for Analysis | Does the document or spreadsheet originate from a known and trusted source? Has there been an increase in DDE-related activity in logs compared to the baseline? Are there any anomalous child processes spawned by Office applications? Is there evidence of recent phishing attempts that could correlate with the DDE payload? |
| Decision for Escalation | Escalate if suspicious DDE activity is confirmed, especially if associated with known indicators of compromise (IOCs) or if linked to attempted phishing incidents. Also, escalate if there are unexplained or unauthorized registry changes enabling DDE. |
| Additional Analysis Steps for L1 | Verify the legitimacy of suspicious documents by cross-referencing originating sources. Correlate detected DDE activity with user login patterns and timestamps. Analyze network activity for any suspicious outbound connections related to DDE execution. |
| T2 Analyst Actions | Conduct deeper forensic analysis on systems exhibiting DDE behavior. Capture and analyze memory dumps of involved processes for any latent malicious code. Review and correlate additional logs or telemetry from endpoint protection tools to confirm malicious activity. |
| Containment and Further Analysis | Isolate affected systems to prevent lateral movement. Use endpoint detection and response (EDR) tools to terminate malicious processes. Conduct a full disk analysis to identify other potential compromises or persistence mechanisms. Review user permissions and modify access rights if unauthorized changes are detected. |
