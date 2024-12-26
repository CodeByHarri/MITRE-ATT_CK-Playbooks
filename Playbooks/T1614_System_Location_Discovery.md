# System_Location_Discovery - T1614

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Discovery |
| MITRE TTP | T1614 |
| MITRE Sub-TTP | T1614 |
| Name | System Location Discovery |
| Log Sources to Investigate | Monitor system logs for any use of system location discovery tools or APIs such as GetLocaleInfoW. Additionally, analyze logs from cloud environment metadata services (AWS, Azure) to detect instances accessing availability zone metadata. Check network traffic logs for connections to external IP geolocation services, and review endpoint detection solution logs for unusual geolocation queries. |
| Key Indicators | Detection of the GetLocaleInfoW API call in logs, accessing cloud metadata instance for availability zone information, network traffic to known IP geolocation services, and changes or queries relating to time zone, keyboard layout, or language settings. |
| Questions for Analysis | Is the detected activity expected for the host or user based on typical behavior and operational requirements? Does the geolocation or host data query align with a known legitimate purpose, or is it observed alongside other suspicious activities? Has similar behavior been detected from the same IP or user account recently? |
| Decision for Escalation | Escalate to Tier 2 if the queries are coupled with suspicious network activity, if there are no legitimate business operations justifying geolocation or host data queries, or if the queries are executed by a process with no valid reason to perform such actions. |
| Additional Analysis Steps for L1 | Correlate timestamps of location discovery API calls with user activity logs to verify if associated with user login or remote access. Validate whether external IP-based geolocation services are commonly accessed in legitimate software functions. Review any concurrent suspicious activities or alerts, such as unusual outbound network connections. |
| T2 Analyst Actions | Investigate the broader context of the situation by analyzing related logs, such as recent system changes, alerts on potentially malicious software, or unusual user account activities. Conduct deeper endpoint analysis for presence of RATs or other malware that could manipulate location data. Assess for potential command and control (C2) communication if corroborated with external IP lookups. |
| Containment and Further Analysis | If confirmed malicious, isolate the affected system from the network to prevent further data leakage. Conduct a thorough investigation to identify and neutralize any malicious software. Update detection and prevention policies in endpoint protection to mitigate future risks. Inform relevant stakeholders and prepare a report detailing the incident for organizational awareness and response adjustments. |
