# Compromise_Host_Software_Binary - T1554

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1554 |
| MITRE Sub-TTP | T1554 |
| Name | Compromise Host Software Binary |
| Log Sources to Investigate | Investigate file integrity monitoring logs (e.g., tripwire logs), EDR/antivirus logs for alerts on modified binaries, system logs showing unexpected binary updates, package manager logs (for Linux, check "/var/log/yum.log" for version lock usages), and application logs pertaining to high-usage binaries (e.g., SSH, FTP, etc.). |
| Key Indicators | Changes to common executable binaries (e.g., SSH, FTP clients) without corresponding update processes, detected trojan/backdoor signatures in these binaries, binary hashes that do not match known-good versions, and use of 'versionlock' configurations in package managers preventing updates. |
| Questions for Analysis | Were there any recent system updates or legitimate installations that could explain the modification? Are the altered binaries currently in use or associated with uncommon parent processes? Is there evidence of similar changes on other systems within the network? |
| Decision for Escalation | Escalate to Tier 2 if unauthorized binary modifications are confirmed, if backdoor or trojan code is found within a binary, or if modifications correlate with suspicious or unauthorized network traffic. |
| Additional Analysis Steps for L1 | Verify the hash values of suspicious binaries against known-good control hashes. Look for patterns of repeated unauthorized changes in system binaries. Check correlation with recent package management or patch activities. |
| T2 Analyst Actions | Conduct a deeper forensic analysis on the affected files, including their metadata and associated processes. Validate whether any similar modifications exist across the network. Use reverse engineering techniques to understand any inserted malicious code. |
| Containment and Further Analysis | Quarantine and replace affected binaries with clean versions. Isolate the system for further analysis to prevent lateral movement. Investigate how the compromise occurred (e.g., through exploit or credential theft) and apply compensating controls such as enhanced monitoring or patching. Conduct memory forensics if live processes are linked to compromised binaries. |
