# Application_Layer_Protocol:_File_Transfer_Protocols - T1071002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1071.002 |
| MITRE Sub-TTP | T1071.002 |
| Name | Application Layer Protocol: File Transfer Protocols |
| Log Sources to Investigate | Network traffic logs for protocols like SMB, FTP, FTPS, and TFTP. Review firewall logs, intrusion detection systems (IDS), and intrusion prevention systems (IPS) for anomalous file transfer activities. Additionally, check endpoint logs for unusual processes initiating connections over these protocols. |
| Key Indicators | Unusual file transfer activity, particularly large or unexpected file sizes. Connections to external IPs or domains that are not part of typical business operations or geolocations. Consistent file transfers outside of normal business hours or high frequency of small file transfers. Repeated failed login attempts followed by a successful one in FTP logs. |
| Questions for Analysis | Are there unusual spikes in data transfer size or frequency? Is the destination IP/domain known and part of regular business operations? Did the file transfer occur during odd hours or was it initiated by an uncommon user account or process? |
| Decision for Escalation | Escalate if the destination of the file transfer is unknown or suspicious, if the data size is abnormally large, or if the activity correlates with other suspicious behaviors like failed logins or remote command execution attempts. |
| Additional Analysis Steps for L1 | Verify the IP addresses involved with a threat intelligence database for any known malicious activity. Cross-check user accounts and processes that initiated the transfers against HR and regular activity records. Confirm whether the file transfer aligns with known business needs or scheduled tasks. |
| T2 Analyst Actions | Conduct deeper inspection of the transferred files for malware or hidden data. Use network packet analysis to identify any anomalies in the protocol fields. Review historical data for patterns indicating persistent C2 communication. If possible, simulate the file transfer in a controlled environment to observe protocol behavior. |
| Containment and Further Analysis | Restrict outbound connections from affected systems to the identified malicious IPs while ensuring business operations are not disrupted. Initiate a threat hunt to identify other systems potentially compromised. Collaborate with IT to apply network segmentation and strengthen monitoring around critical assets. |
