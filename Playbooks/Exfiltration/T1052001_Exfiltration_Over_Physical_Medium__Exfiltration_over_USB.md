# Exfiltration_Over_Physical_Medium:_Exfiltration_over_USB - T1052001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Exfiltration |
| MITRE TTP | T1052.001 |
| MITRE Sub-TTP | T1052.001 |
| Name | Exfiltration Over Physical Medium: Exfiltration over USB |
| Log Sources to Investigate | File system logs, USB device connection logs, and DLP (Data Loss Prevention) system alerts. Examples include Windows Event Logs (especially events 2001, 2003 related to USB device connection), Sysmon logs for process creations and file operations involving USB drives, and DLP logs indicating data transfers to removable media. |
| Key Indicators | Frequent or large data transfers to USB devices, unusual USB plug-in at odd hours, unauthorized USB devices, file copy operations to USB drives, and alert logs from DLP involving sensitive data transfer to USB devices. |
| Questions for Analysis | Was the USB connected to a secure or restricted system? Is there a record of the same USB device transferring data frequently? Is the user associated with the USB connection authorized to transfer the types of files accessed? Were the files copied to the USB device sensitive or classified? |
| Decision for Escalation | Escalate to Tier 2 if non-standard or unauthorized USB devices are used, if there's evidence of transfer of large or sensitive files, or if the data is moved from a critical or air-gapped system. Additionally, escalate if the USB activity is outside of normal working hours with no valid business justification. |
| Additional Analysis Steps for L1 | Verify recent USB device logs for connection times and user account associations. Check for DLP alerts related to this USB activity. Correlate file access logs around the time of USB connection. Attempt to verify user activity and purpose for data transfer. |
| T2 Analyst Actions | Conduct a deeper investigation into the user’s actions and behavior, review user profile for any past suspicious activities, check for any correlating incidents on other systems, verify authenticity of USB device with physical security logs, and monitor network for similar activities from the same or linked user accounts. |
| Containment and Further Analysis | Disable the USB port until the investigation is complete. If data exfiltration is confirmed, conduct a full-scale data breach investigation. Review and enhance USB policies, ensure endpoint DLP measures are effective, interview involved personnel, and apply additional monitoring on affected systems. Coordinate with physical security to track USB devices entering secure areas. |
