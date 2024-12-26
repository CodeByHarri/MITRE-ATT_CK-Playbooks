# Boot_or_Logon_Autostart_Execution - T1547

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1547 |
| MITRE Sub-TTP | T1547 |
| Name | Boot or Logon Autostart Execution |
| Log Sources to Investigate | Monitor Windows Event Logs for Event ID 7045 (Service Installed), Event ID 13 (Registry modifications), and Event ID 5857, 5858 (Windows Defender detections). Check startup folders and Windows Registry keys like 'HKLM\Software\Microsoft\Windows\CurrentVersion\Run' and 'HKCU\Software\Microsoft\Windows\CurrentVersion\Run'. On Linux, investigate the '/etc/init.d', '/etc/rc.local', and '/etc/systemd/system' directories for suspicious entries. |
| Key Indicators | New or modified entries in Windows Registry Run keys or system startup folders. Unexpected or suspicious services being installed. Unusual programs configured to start automatically, especially those that do not match with typical system maintenance or user-installed applications. |
| Questions for Analysis | Has there been a recent logon event that coincides with the creation of a new startup item? Does the program set to autostart match with known legitimate software, or is it linked to known malware? Are there any associated alerts from antivirus or endpoint detection solutions for the files being executed on startup? |
| Decision for Escalation | Escalate if the startup entry is linked to known malicious software or behaviors. Escalate if manual investigation confirms manipulation of startup items without legitimate justification, particularly if tied to recent suspicious user activity or associated with other security alerts. |
| Additional Analysis Steps for L1 | Verify the file path and signatures of any executable set to autostart, comparing them against threat intelligence databases for known bad hashes. Search organizational communications to ensure new software installations or updates were not recently approved. Check recent user activity and login locations/times for anomalies. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of the executable file's properties and history on the system. Correlate the startup modifications with network activity logs to determine potential lateral movement or data exfiltration activities. Use sandbox technology to safely execute suspicious files in a controlled environment. |
| Containment and Further Analysis | Quarantine the suspicious executable and remove the unauthorized startup entry. If malicious activity is confirmed, isolate the impacted system from the network. Conduct a full incident response investigation including memory analysis, disk imaging, and further scope out if other connected systems exhibit similar modifications. Advise on updating security tools and policies to prevent reoccurrence. |
