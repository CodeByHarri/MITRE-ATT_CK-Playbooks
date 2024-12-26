# Application_Layer_Protocol:_Publish_Subscribe_Protocols - T1071005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Command and Control |
| MITRE TTP | T1071.005 |
| MITRE Sub-TTP | T1071.005 |
| Name | Application Layer Protocol: Publish/Subscribe Protocols |
| Log Sources to Investigate | Network traffic logs with visibility into application layer protocols, specifically focusing on MQTT, XMPP, AMQP, and STOMP traffic. Firewall logs, proxy logs, and intrusion detection/prevention system (IDS/IPS) logs can provide details about protocol usage and unusual patterns. Event logs from message brokers or middleware systems that support publish/subscribe protocols. |
| Key Indicators | Unusual volumes of pub/sub traffic from a single client, especially if outside normal usage hours. Unexpected connections from devices or IPs that typically don't use pub/sub protocols. Embedded command-like strings or irregular data patterns within pub/sub messages. Traffic directed towards known malicious IPs or domains serving as part of a pub/sub broker. |
| Questions for Analysis | Are the source and destination of the pub/sub traffic within the expected geographical or network boundaries? Does the amount or type of pub/sub traffic deviate significantly from the usual baseline of activity? Is there any known malware signature or indicator of compromise (IOC) associated with the end nodes or message broker in the pub/sub traffic? |
| Decision for Escalation | Escalate to Tier 2 if pub/sub traffic is observed to have originated from or destined to suspicious or unusual network endpoints, if significant deviation from normal traffic patterns is identified, or if traffic contains potential IOCs related to known threats. |
| Additional Analysis Steps for L1 | Cross-reference IPs involved in pub/sub traffic with threat intelligence feeds for IOCs. Check historical logs to identify changes in traffic patterns. Verify whether the applications involved in using pub/sub protocols have legitimate business purposes. |
| T2 Analyst Actions | Conduct deeper packet analysis of the suspicious pub/sub traffic to assess the content and any embedded commands. Utilize threat intelligence to evaluate the context of the identified endpoints and brokers. Engage with incident response if traffic contains or leads to confirmed malicious activity. |
| Containment and Further Analysis | Implement network segmentation to restrict malicious pub/sub traffic. Block malicious IPs or domains. Isolate systems identified as compromised. Conduct a full investigation of affected systems to determine the scope of compromise and execute a forensic analysis to remove any persistent threats. Ensure updated threat intelligence and IOC signatures in detection systems. |
