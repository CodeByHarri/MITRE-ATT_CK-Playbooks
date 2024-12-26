# Traffic_Signaling:_Socket_Filters - T1205002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control, Defense Evasion, Persistence |
| MITRE TTP | T1205.002 |
| MITRE Sub-TTP | T1205.002 |
| Name | Traffic Signaling: Socket Filters |
| Log Sources to Investigate | Network traffic logs, particularly from network sensors or intrusion detection systems like Zeek or Snort. Logs related to socket API activity on endpoints, particularly those featuring the usage of 'libpcap', 'Winpcap', 'pcap_setfilter', or 'setsockopt' functions. System logs indicating unusual listening ports or processes initiating network connections unexpectedly. |
| Key Indicators | Presence of socket filters being attached using 'pcap_setfilter' or 'setsockopt'. Network traffic analysis identifying crafted packets or unusual patterns matching known filter criteria. Detection of reverse shell triggers or unexpected command shell activity following the packet matching event. |
| Questions for Analysis | Are there any unauthorized or suspicious processes initiating network sockets with filtering capabilities? Do system logs indicate the installation of socket filters without a legitimate purpose or process? Is there evidence of network traffic that corresponds with crafted or unexpected packets reaching the endpoints? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed evidence of unauthorized socket filter installation, particularly if it matches patterns associated with known threat actors. Escalate if a reverse shell or command execution is observed following a suspicious network packet receipt. |
| Additional Analysis Steps for L1 | Verify the ownership and purpose of processes using 'libpcap' or 'Winpcap' libraries. Cross-reference with known legitimate software that may use these functions. Analyze network packet captures for specific indicators of crafted packets or anomalous traffic patterns. |
| T2 Analyst Actions | Conduct a deeper forensic analysis of affected systems to trace back the origin and methodology of socket filter installation. Examine the legitimacy and origin of network traffic associated with the socket filters. Engage with threat intelligence to correlate observed activity with known threat actor TTPs or campaigns. |
| Containment and Further Analysis | If a backdoor or implant is confirmed, isolate the affected system from the network immediately to prevent further communication with C2 servers. Conduct a full memory and disk analysis to identify additional artifacts. Strengthen monitoring and detection strategies around network and socket usage going forward. |
