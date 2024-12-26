# Obtain_Capabilities:_Artificial_Intelligence - T1588007

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Resource Development |
| MITRE TTP | T1588.007 |
| MITRE Sub-TTP | T1588.007 |
| Name | Obtain Capabilities: Artificial Intelligence |
| Log Sources to Investigate | Monitor web proxy logs, network traffic logs, DNS logs, and application logs related to AI tool usage. Specifically look for traffic to known AI platforms and services from internal hosts. Review user access logs to detect unauthorized access to AI tools. Collect script execution logs and endpoint activity that might suggest script generation or execution. |
| Key Indicators | Unusual network traffic to AI services (e.g., OpenAI, AI research labs). Abnormal volume of API requests to generative models. Newly created scripts or files that demonstrate characteristics of automated generation, such as lack of human-like touch-ups. High frequency of scripting or compilation activities on user workstations. |
| Questions for Analysis | Have there been unusual spikes in network traffic to AI tool services? Are there new scripts or code that haven't been created previously by the usual developers? Has there been any recent unauthorized or suspicious access to corporate accounts or AI tools? |
| Decision for Escalation | If there is strong evidence of malicious AI tool usage, such as unexplained access patterns or scripts tied to known attack behaviors, escalate to Tier 2. Particularly if the scripts seem to follow a trend seen in phishing campaigns or are designed to perform suspicious activities. |
| Additional Analysis Steps for L1 | Review recent changes in script execution logs. Confirm access to AI tools with identified user authentication logs. Correlate network activity to established baselines of legitimate AI tool usage. |
| T2 Analyst Actions | Conduct detailed forensic analysis of the identified scripts and generated content. Cross-reference with threat intelligence feeds for known malicious use of AI-generated outputs. Engage in deeper inspection of network traffic and communications related to suspect activity. |
| Containment and Further Analysis | Isolate any machine suspected of generating or executing malicious AI-generated scripts. Revoke suspicious account credentials and enforce a password reset. Implement network rules to block unauthorized access to AI services. Conduct a full security audit to identify any further exploitation or misuse of AI tools. |
