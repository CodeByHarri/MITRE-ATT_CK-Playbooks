# Modify_System_Image:_Downgrade_System_Image - T1601002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1601.002 |
| MITRE Sub-TTP | T1601.002 |
| Name | Modify System Image: Downgrade System Image |
| Log Sources to Investigate | Network device logs (e.g., Cisco, Juniper), configuration management systems, syslogs, network traffic analysis tools, and version control logs for any changes in system image files. Also, look at logs from network management systems that record firmware or software updates/downgrades. |
| Key Indicators | Unexpected changes in the OS version on network devices, logs showing boot from an unauthorized system image file, reduction in encryption strength or security features enabled, anomalous device configuration changes, and alerts from integrity monitoring systems. |
| Questions for Analysis | Was there an authorized change request for the system image version downgrade? Are there recent logs showing a system reboot? Is there a pattern of unauthorized access attempts to the device? Has there been a recent reported vulnerability associated with the older OS version now running? |
| Decision for Escalation | Escalate to Tier 2 if the system image downgrade was not documented or authorized, if there is evidence of unauthorized access, or if the device is critical to network security or operations and is now running a vulnerable OS version. |
| Additional Analysis Steps for L1 | Verify the current OS version against the expected version in asset inventory. Check for any associated change management tickets. Review recent login activity on the device. Check if the downgrade correlates with any recent vulnerabilities or advisories. |
| T2 Analyst Actions | Investigate whether the system image file was modified or replaced recently. Review historical configuration and operation logs for indicators of unauthorized actions. Cross-check with known exploit timelines for the downgraded OS. Perform a detailed risk assessment on the vulnerable configuration introduced by the downgrade. |
| Containment and Further Analysis | Ensure the device configuration is reverted to a secure, updated OS version. Implement additional logging and monitoring on the affected device. If necessary, isolate the device to prevent further compromise. Conduct a full review of access permissions and authentication methods to prevent similar incidents. Consider revisiting policies on firmware and OS management and enforce stricter change control. |
