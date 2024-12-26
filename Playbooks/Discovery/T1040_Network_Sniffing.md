# Network_Sniffing - T1040

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access, Discovery |
| MITRE TTP | T1040 |
| MITRE Sub-TTP | T1040 |
| Name | Network Sniffing |
| Log Sources to Investigate | Investigate logs from network monitoring tools such as Wireshark, Zeek (formerly Bro), and NetFlow data for unusual patterns or active reconnaissance. SNMP logs and device configuration changes should be reviewed to detect any unauthorized network interface configuration. Cloud logs, such as AWS CloudTrail, GCP Cloud Logging, and Azure Monitor, can provide insights into the use of traffic mirroring services. Look at logs from Intrusion Detection Systems (IDS) for evidence of suspicious network capture activity. |
| Key Indicators | Indicators include network interfaces configured in promiscuous mode, unexpected network traffic on span ports, presence of packet capture software, sudden spike in network data captured, unauthorized traffic mirroring changes in cloud environments, and unusual commands executed on network devices such as 'monitor capture'. |
| Questions for Analysis | Has the network interface been put into promiscuous mode without proper authorization? Are there any unauthorized traffic mirroring configurations in the cloud environment? Is there a higher volume of network data being transferred than usual? Are there specific network packets that contain cleartext sensitive information? |
| Decision for Escalation | Escalate to Tier 2 if signs of suspicious or unauthorized network sniffing activity are observed, such as the detection of interfaces in promiscuous mode, unauthorized access to traffic mirroring services, or evidence of traffic capture tools in use that are not approved by IT policies. |
| Additional Analysis Steps for L1 | Verify the legitimacy of network monitoring tools and network interface configurations. Review user access logs for recent account activities related to network configuration changes. Check for anomalies in network patterns. Validate the use of network packet capturing tools against the organization's inventory of sanctioned tools. |
| T2 Analyst Actions | Perform a deeper investigation into the logs to confirm unauthorized access or use of packet capturing tools. Analyze the packet data for sensitive information leaks. Correlate log data across IT and cloud infrastructure to identify potential patterns of a larger threat campaign. Work with IT to verify any suspicious network configurations. |
| Containment and Further Analysis | Disconnect any suspected interfaces running in promiscuous mode. Disable unauthorized traffic mirroring configurations. Educate users on the risks associated with network sniffing. Conduct a full network scan to ensure no unauthorized tools are running. If necessary, engage with the network team to conduct a broader forensic analysis. Consider refreshing encryption protocols to protect against future exposures of sensitive data over the network. |
