# Stage_Capabilities:_Upload_Malware - T1608001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1608.001 |
| MITRE Sub-TTP | T1608.001 |
| Name | Stage Capabilities: Upload Malware |
| Log Sources to Investigate | Evaluate web server access logs for any unusual upload activity, such as large files or unusual file types being uploaded. Review API call logs for services like GitHub or AWS to detect any unauthorized uploads. Network traffic logs should be scanned for connections to known or suspicious third-party hosting services like IPFS or Pastebin. Check DNS logs for queries to domains associated with malicious hosting platforms. |
| Key Indicators | Sudden uploads of large files to external storage or content delivery services. Uncommon or rare file types being uploaded to the web server. Network connections to IP addresses associated with known malicious infrastructure. API keys being used outside normal business hours or from unexpected geolocations. |
| Questions for Analysis | Is the file upload activity consistent with known business processes? Do the source IP addresses match expected locations for the organization? Does the timing of uploads correspond to any suspicious network activities? Are there any reports on the external infrastructure that is being connected to or used for uploads? |
| Decision for Escalation | Escalate to Tier 2 if any unauthorized uploads are detected, particularly to known malicious or suspicious infrastructure. If an organization's sensitive or proprietary data is identified in uploaded files, or if uploads are associated with atypical network activity, escalate immediately. |
| Additional Analysis Steps for L1 | Correlate found indicators with threat intelligence feeds to look for matches. Validate user identity associated with the upload activities through IAM logs. Check endpoint logs for any sign of malware or suspicious processes that match the uploaded files. |
| T2 Analyst Actions | Conduct deeper analysis on the origin of uploaded files, including reverse engineering the contents if possible. Analyze the unusual patterns in network traffic around the time of the uploads. Engage with the intelligence team to see if there are any reports on the infrastructure or techniques used. |
| Containment and Further Analysis | Block access to IPs or domains identified as hosting or facilitating the spread of malicious content. Initiate investigation into the source of unauthorized uploads, secure potential compromised accounts using multi-factor authentication (MFA) or password resets. If malware is detected, follow incident response protocols to eliminate threats and assess any potential data loss or impact. |
