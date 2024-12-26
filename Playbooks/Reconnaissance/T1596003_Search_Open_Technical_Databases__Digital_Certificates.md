# Search_Open_Technical_Databases:_Digital_Certificates - T1596003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1596.003 |
| MITRE Sub-TTP | T1596.003 |
| Name | Search Open Technical Databases: Digital Certificates |
| Log Sources to Investigate | Monitor network traffic logs for unusual SSL/TLS handshake patterns, high-volume queries towards digital certificate authority domains or APIs, and usage of certificate lookup services (e.g., SSLShopper). Examine web server access and error logs to detect incoming traffic from known external IPs associated with reconnaissance tools. Additionally, review public key infrastructure (PKI) activity logs within the organization for any suspicious certificate queries or anomalies. |
| Key Indicators | Frequent access to certificate lookup services from internal IPs, unusual patterns in SSL/TLS handshake requests, elevated numbers of failed certificate verifications, queries to external digital certificate authority domains from unusual locations, and anomalies in PKI-related logs. |
| Questions for Analysis | Are the observed activities originating from known and trusted IP addresses or new/unusual ones? Is there a legitimate business purpose for accessing digital certificate lookup services? Do these activities correlate with any current or planned network changes or public-facing services? |
| Decision for Escalation | Escalation to Tier 2 is warranted if the source of the activity cannot be verified as legitimate, if there is evidence of coordination with other suspicious activities (e.g., phishing attempts or external scans), or if the access to digital certificate data is from a high-risk location. |
| Additional Analysis Steps for L1 | 1. Validate the list of accessed digital certificate authority domains with IT for known operations.<br>2. Check whether the IP addresses accessing the lookup services are part of any recognized threat intelligence feeds.<br>3. Correlate certificate lookup activity with active security alerts and recent application deployments. |
| T2 Analyst Actions | 1. Perform a deeper forensic analysis of the network traffic to identify patterns or anomalies.<br>2. Investigate the legitimacy of the IP addresses and domains interacting with corporate resources using threat intelligence platforms.<br>3. Verify any new certificates added since the suspicious activity and ensure they are sanctioned by the organization. |
| Containment and Further Analysis | 1. Immediately block any identified malicious IPs or domains from further interaction.<br>2. Initiate internal reviews of the PKI infrastructure and digital certificate management processes to ensure no exploitation.<br>3. Use sandbox environments to analyze any related artifacts or scripts recovered during the investigation for malware or reconnaissance capabilities. |
