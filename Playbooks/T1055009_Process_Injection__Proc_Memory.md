# Process_Injection:_Proc_Memory - T1055009

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion, Privilege Escalation |
| MITRE TTP | T1055.009 |
| MITRE Sub-TTP | T1055.009 |
| Name | Process Injection: Proc Memory |
| Log Sources to Investigate | Monitor logs from Linux process activity, specifically /proc file system access logs, including /proc/[pid]/maps and /proc/[pid]/mem. System call logs (such as syscall auditing via auditd) to identify unusual write operations or memory mappings, and logs from intrusion detection systems (IDS) that may capture anomalous process behaviors. Cross-reference these with file integrity monitoring system logs and alerts. |
| Key Indicators | Access or modification of the /proc/[pid]/maps or /proc/[pid]/mem paths by non-standard or unexpected processes. Unusual patterns of memory access, particularly frequent or unexpected writes to memory space of running processes. Abnormal process hierarchy or execution context deviation, such as a non-shell process performing actions often associated with a shell or developer tool. |
| Questions for Analysis | 1. Is the process accessing /proc/[pid]/maps or /proc/[pid]/mem expected to perform such actions, or is it outside its normal activity spectrum?<br>2. Are there any recent changes or updates applied on the system that might justify this behavior?<br>3. Is there any evidence of privilege escalation or unauthorized access prior to these actions? |
| Decision for Escalation | Escalate to Tier 2 if access to critical processes is noted, especially if the process attempting injections has no legitimate reason to do so. Escalate if the accessed process is a high-value target (e.g., a system service or security software), or if there are concurrent signs of privilege escalation activities on the system. |
| Additional Analysis Steps for L1 | Validate if the behavior is consistent with recent system changes or updates. Review related system event logs for any signs of lateral movement or privilege escalation. Correlate with user activity logs and any relevant alerts from endpoint security systems. |
| T2 Analyst Actions | Perform deeper inspection of the injected process and its memory state. Utilize memory forensic tools to verify the presence of ROP payloads. Cross-reference with known threat intelligence pertaining to such injection techniques. Review network logs for any outbound connections from the compromised process, especially towards known C2 IPs. |
| Containment and Further Analysis | Isolate affected systems by restricting network access. Capture and preserve a memory dump of the affected systems for in-depth forensic analysis. Remove any detected persistence mechanisms. If malicious activity is confirmed, reset credentials and audit access to similar systems to ensure no lateral movement occurred. |
