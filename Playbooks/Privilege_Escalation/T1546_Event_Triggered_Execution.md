# Event_Triggered_Execution - T1546

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1546 |
| MITRE Sub-TTP | T1546 |
| Name | Event Triggered Execution |
| Log Sources to Investigate | Review event logs such as Windows Event Log for entries related to Task Scheduler, WMI subscriptions/logs, and application logs that show processes triggered unexpectedly, especially under SYSTEM or service account contexts. For Linux systems, investigate cron jobs and init scripts. In cloud environments, inspect cloud event logs related to various triggering sources like AWS CloudWatch Events, Azure Event Hubs, or Google Cloud Functions. |
| Key Indicators | Look for unexpected event trigger modifications or creations, such as new tasks in Task Scheduler, new WMI Event Consumer or Filter creation. In Linux, new or modified cron jobs or init scripts with unexpected timings or commands. In cloud logs, detect new rules or events that deviate from normal operation (e.g., unexpected lambda invocations). Monitor for execution of scripts/programs that should not normally be scheduled or event-triggered. |
| Questions for Analysis | Has there been any recent administrative changes that could account for newly configured tasks or event triggers? Are the triggered processes or scripts familiar, or do they belong to known software? Do triggered events correlate with legitimate user activities or seem anomalous considering the timing or context? |
| Decision for Escalation | Escalate if triggered processes are launching in unusual contexts or times, especially if no legitimate change requests or system updates correlate. Escalate also if any detected scripts or binaries are confirmed malicious or originate from suspicious locations. |
| Additional Analysis Steps for L1 | Verify the sources and timestamps of the triggers; compare with user activity and any ongoing administrative tasks. Check if the events or processes have known relations to specific legitimate software applications. Check for known malicious hashes or attributes. |
| T2 Analyst Actions | Conduct a deeper investigation on the triggered processes or scripts, analyzing binaries for known malware characteristics or unusual network behaviors. Correlate with threat intelligence feeds for indicators. Review user account permissions for anomalies that might have allowed modification of triggers. |
| Containment and Further Analysis | Disable or remove maliciously modified or created event triggers immediately, ensuring minimal operational disruption. Restore any altered system configurations to their original states if possible. Follow up with a thorough scan of the affected system for any implants or secondary backdoors. Report findings for wider organizational awareness and prevention. Ensure continuous monitoring and alerting for similar suspicious events. |
