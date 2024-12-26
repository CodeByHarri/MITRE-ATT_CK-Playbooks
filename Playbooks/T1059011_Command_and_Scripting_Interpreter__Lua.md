# Command_and_Scripting_Interpreter:_Lua - T1059011

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Execution |
| MITRE TTP | T1059.011 |
| MITRE Sub-TTP | T1059.011 |
| Name | Command and Scripting Interpreter: Lua |
| Log Sources to Investigate | Monitor system logs for unusual Lua script execution. Log sources should include application logs where Lua is embedded, such as gaming applications or user-installed software. Network logs and firewall logs should be reviewed for unusual traffic patterns that could indicate Lua scripts being downloaded or executed remotely. SIEM data should be evaluated for patterns of Lua interpreter execution at unexpected times or from unauthorized users. |
| Key Indicators | Frequent execution of the Lua interpreter or '.lua' scripts, especially on machines or accounts not commonly using Lua. Review of scripting errors in application logs indicating malicious usage. Network traffic to known malicious IP addresses where Lua-based payloads have previously been sent. Sudden increase in resource usage by processes involving Lua. |
| Questions for Analysis | Is the Lua interpreter being used on systems that do not normally require it? Are there indicators that the Lua script was downloaded from an unverified or malicious site? Is there an unexpected network connection associated with the Lua script activity? Is the script execution consistent with legitimate use cases within the organization? |
| Decision for Escalation | Escalate to Tier 2 if: Lua script execution is detected on systems that typically do not use Lua, there is confirmed interaction with known malicious infrastructure, or unauthorized access and privilege escalation attempts coincide with the script execution. |
| Additional Analysis Steps for L1 | Verify if the Lua interpreter or scripts were installed recently and whether this correlates with software changes or updates. Cross-reference the execution events with personnel schedules or business processes that may require Lua script usage. Check for any anomalous child process creation spurred from Lua scripts. |
| T2 Analyst Actions | Conduct a deep dive into the recent system changes and scrutinize other systems for similar indicators of Lua usage. Correlate Lua script invocations with network traffic to identify potential command and control communications. Identify any persistence mechanisms that might have been implanted via Lua scripts. |
| Containment and Further Analysis | Isolate affected systems and reset credentials to prevent further unauthorized access. Capture and analyze the Lua scripts and interpret their functionality in a controlled environment. Work with IT to scan the network for other potential instances of malicious Lua activities or infected machines. Implement strict access controls and monitoring on Lua interpreter usage. |
