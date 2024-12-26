# Firmware_Corruption - T1495

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Impact |
| MITRE TTP | T1495 |
| MITRE Sub-TTP | T1495 |
| Name | Firmware Corruption |
| Log Sources to Investigate | System BIOS logs, UEFI firmware logs, hardware diagnostic logs, operating system boot logs, and vendor-specific firmware update logs. Examples include Windows Event Logs associated with boot processes (e.g., Event ID 41 - Kernel-Power), logs from firmware management tools like Intel Management Engine BIOS Extension (MEBx), and logs from network monitoring tools if network device firmware is targeted. |
| Key Indicators | Unexpected reboots or the system failing to boot at all, errors during BIOS/UEFI startup processes, manipulation of firmware-related files, unexpected firmware updates or re-flashing activities, unauthorized access to BIOS configuration settings, and unusual disconnects/downtime of network devices possibly caused by firmware corruption. |
| Questions for Analysis | 1. Is there evidence of recent unauthorized access attempts on firmware-related components or settings?<br>2. Have there been recent unexpected firmware update processes?<br>3. Are there any logs indicating tampering or corruption of firmware? 4. Are affected devices experiencing boot failures or unexpected behavior that aligns with known firmware corruption symptoms? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed unauthorized modification of firmware settings, successful execution of unauthorized firmware re-flash activities, multiple devices reporting similar errors suggesting a systemic attack, or any indicators of potential widespread data destruction linked to compromised firmware. |
| Additional Analysis Steps for L1 | Verify the integrity of firmware by checking hashes against known good values, identify patterns in reboot logs that may indicate system instability due to firmware issues, cross-reference detected events with known firmware exploits or vulnerabilities, and review any recent changes or updates to firmware settings or configurations. |
| T2 Analyst Actions | Perform a deeper forensic analysis of affected systems to confirm the presence of unauthorized modifications, analyze network traffic for signs of an attacker attempting to deploy firmware-focused exploits, consult with hardware vendors for known vulnerabilities or issues, and acquire images of firmware for detailed analysis and possible restoration. |
| Containment and Further Analysis | Isolate affected systems to prevent further spread of corruption or data loss, restore backup images of firmware to mitigate integrity issues, update and apply security patches to prevent exploitation, engage with firmware vendors for targeted remediation strategies, and increase monitoring of related systems for signs of further activity. |
