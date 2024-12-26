# Adversary-in-the-Middle - T1557

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Collection, Credential Access |
| MITRE TTP | T1557 |
| MITRE Sub-TTP | T1557 |
| Name | Adversary-in-the-Middle |
| Log Sources to Investigate | Investigate DNS logs to detect unusual changes in DNS settings that may indicate manipulation. Analyze ARP tables and ARP logs for spoofing attempts. Review network traffic logs for signs of AiTM activity, such as unexpected routing paths, data manipulations, or communications with known malicious IPs. Check for SSL/TLS negotiation logs to identify downgrade attacks or weak protocol usage. |
| Key Indicators | Sudden changes in DNS settings without authorization. Requests or redirects to suspicious domains. Unusual ARP responses indicating possible spoofing. Network traffic routed through unexpected intermediaries. Evidence of SSL/TLS downgrades or deprecated protocols being negotiated. Communications with known malicious IP addresses. |
| Questions for Analysis | Are there unauthorized changes in DNS settings? Is there evidence of ARP spoofing in the network traffic? Are users being redirected to suspicious or known-malicious domains? Have there been unexpected SSL/TLS downgrade negotiations? Are there connections to or from known malicious IPs? |
| Decision for Escalation | Escalate to Tier 2 if there is confirmed evidence of DNS or ARP manipulation, suspicious redirection of traffic, SSL/TLS downgrades without legitimate explanation, or interaction with known malicious IPs or domains. |
| Additional Analysis Steps for L1 | Verify network device integrity and conformity with standard configurations. Investigate the source and intention of the DNS changes. Validate the legitimacy of the ARP entries or potential spoofing attempts. Identify the origin of any SSL/TLS downgrade negotiations. |
| T2 Analyst Actions | Conduct a deeper investigation of network traffic to identify patterns or signatures typical of AiTM attacks. Collaborate with IT to restore legitimate DNS and ARP configurations. Validate SSL/TLS settings across all networked devices. Liaise with threat intelligence to correlate suspicious IP/Domain with known threat actors. |
| Containment and Further Analysis | Revert any unauthorized DNS configurations and bolster DNS security controls. Implement stricter ARP-spoofing protections and network segmentation policies. Use secure protocols and force-only strong SSL/TLS versions. Monitor affected systems closely for any signs of persistence or secondary attacks. |
