# Server_Software_Component:_Transport_Agent - T1505002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1505.002 |
| MITRE Sub-TTP | T1505.002 |
| Name | Server Software Component: Transport Agent |
| Log Sources to Investigate | Focus on Microsoft Exchange Server logs, especially those related to transport agent operations. Relevant examples include Exchange Message Tracking logs, Exchange Cmdlet logs, and Windows Event Logs (particular attention to events related to .NET assemblies and Exchange transport configurations). Additionally, review any application-level logging that tracks modifications to transport agents or changes to server configurations. |
| Key Indicators | Look for unusual registration of new transport agents. Indicators include unexpected assembly registrations, transport agent configurations that do not match typical operations, and agents acting upon specific email addresses that seem out of the ordinary. Check for repetitive access to sensitive data patterns or email filters that only trigger on certain conditions. |
| Questions for Analysis | 1. Are there any recent changes to transport agent configurations?<br>2. Do the registered agents have any anomalous properties or unusual behavior patterns?<br>3. Are there specific email addresses or patterns targeted by the transport agent? 4. Has there been an increase in copying or accessing email attachments? |
| Decision for Escalation | Escalate to Tier 2 if there are changes to transport agents that cannot be linked to known administrative actions or documented configuration changes, suspicious patterns in email traffic linked to specific agents, or indications of data exfiltration attempts. |
| Additional Analysis Steps for L1 | 1. Verify the legitimacy of transport agent registrations by checking against known changes and updates.<br>2. Examine email headers and attachments for any signs of unauthorized manipulation or addition.<br>3. Correlate new agent registrations with recent administrative activity. |
| T2 Analyst Actions | 1. Conduct a deeper forensic examination of the affected system to identify the time and source of transport agent changes.<br>2. Review any associated .NET assemblies for malicious code that could be indicative of larger threats.<br>3. Establish a timeline of modifications to correlate with any known attacker activities or breach alerts. |
| Containment and Further Analysis | If a malicious transport agent is confirmed, promptly disable or remove the agent and perform a full security audit of the Exchange environment. Assess the potential impact on in-transit data and consider notifying affected users. Implement stricter controls and monitoring around transport agent registration and execution. |
