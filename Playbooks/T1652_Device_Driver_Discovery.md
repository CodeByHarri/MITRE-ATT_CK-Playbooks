# Device_Driver_Discovery - T1652

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1652 |
| MITRE Sub-TTP | T1652 |
| Name | Device Driver Discovery |
| Log Sources to Investigate | Investigate logs from host-based monitoring solutions such as Sysmon or Endpoint Detection and Response (EDR) tools that track process execution and API usage. Specifically, look for process creation events that involve `driverquery.exe`, `lsmod`, `modinfo`, or use of the `EnumDeviceDrivers()` API function. Additionally, review Windows Event Logs (e.g., Security and System logs), Linux audit logs, and macOS Unified logs for suspicious activities related to driver enumeration. |
| Key Indicators | Key indicators include process execution of `driverquery.exe` on Windows, `lsmod` or `modinfo` on Linux/macOS. Unexpected or unauthorized use of the `EnumDeviceDrivers()` API or registry access related to drivers is also critical. High-frequency or unusual timing of these activities could indicate reconnaissance. |
| Questions for Analysis | Is the device driver discovery being performed by a known and authorized user or process? Is there a history of similar behavior on this system? Were any other suspicious activities logged around the same time? Are there unusual patterns in the timing, such as outside of normal business hours? |
| Decision for Escalation | Escalate to Tier 2 if the activity is executed by an unknown, unauthorized, or compromised account, if there are additional indicators of compromise (IOCs) in proximity to this event, or if this activity is part of a suspected larger attack pattern or campaign. |
| Additional Analysis Steps for L1 | Validate the process execution against known software behavior and user actions, review contextual data surrounding the event for anomalies, and check against enterprise security policies regarding device driver interactions. Review recent activities of the involved accounts for anomalies. |
| T2 Analyst Actions | Conduct a deep dive into historical logs for patterns of execution or anomalies, validate against threat intelligence sources for known exploits, and investigate any parallel suspicious activities or deviations from baseline activity on the host. |
| Containment and Further Analysis | If malicious activity is confirmed, isolate the affected system from the network to prevent further spread or data exfiltration. Perform a full forensic analysis of the affected system, reviewing the memory, disk, and network traffic. Identify exploitation attempts against device drivers and assess them for potential privilege escalation paths. Implement further preventive controls, such as application whitelisting or further restrictions on system utilities. |
