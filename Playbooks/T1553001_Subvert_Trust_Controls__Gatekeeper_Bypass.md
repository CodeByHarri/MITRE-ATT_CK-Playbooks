# Subvert_Trust_Controls:_Gatekeeper_Bypass - T1553001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1553.001 |
| MITRE Sub-TTP | T1553.001 |
| Name | Subvert Trust Controls: Gatekeeper Bypass |
| Log Sources to Investigate | System logs such as `/var/log/install.log` or unified logs accessible via Console on macOS can provide information on app installations and Gatekeeper checks. Additionally, check File System Activity logs for modifications to `com.apple.quarantine` attributes and security management logs that might record Gatekeeper bypass events. |
| Key Indicators | 1. Presence of applications or files without a `com.apple.quarantine` attribute after being downloaded from the internet.<br>2. Logs showing execution of previously quarantined apps without associated user interaction.<br>3. Unexpected changes in security policies or failed code signing/notarization checks logged by macOS Gatekeeper. |
| Questions for Analysis | 1. Is there evidence that the quarantine attribute was removed or altered on this file?<br>2. Does the file in question show signs of being altered post its initial execution or download installment?<br>3. Are there any known vulnerabilities or misconfigurations that could have been exploited by the application detected? |
| Decision for Escalation | Escalate to Tier 2 if: 1. Confirmation of quarantine attribute modification or removal without legitimate user action.<br>2. Evidence of Gatekeeper checks being bypassed for a critical or sensitive application.<br>3. Detection of associated activities like unauthorized code execution attempts or downloading large amounts of data outside business needs. |
| Additional Analysis Steps for L1 | Check the digital signature and notarization status of the suspicious app using `codesign` and `spctl` commands. Analyze the quarantine attribute and history of file modifications via `ls -l@` and `xattr` commands. Look for associated network connections or any suspicious download activities at the time of detection. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of the system to trace back the entry point for the bypass. Perform a retroactive review of related Gatekeeper activities and quarantine modifications. Determine if there are copies or similar executables present across other systems within the network, suggesting potential spread of the issue. |
| Containment and Further Analysis | Isolate the affected machine from the network to prevent any further execution of untrusted apps. Reapply Gatekeeper policies and ensure all un-notarized or unsigned software is blocked. Review macOS logs for any signs of persistence mechanisms or other malicious activities. Consider reinstalling macOS from a known good backup if system integrity is compromised. |
