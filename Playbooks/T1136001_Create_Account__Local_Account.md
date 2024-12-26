# Create_Account:_Local_Account - T1136001

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence |
| MITRE TTP | T1136.001 |
| MITRE Sub-TTP | T1136.001 |
| Name | Create Account: Local Account |
| Log Sources to Investigate | Investigate logs from Windows Event Logs, specifically Security logs with Event ID 4720 for account creation events. On macOS, review the system logs for 'dscl' or 'create' commands. For network devices, check CLI command logs for 'username' or similar commands. When dealing with Kubernetes, review audit logs to detect the use of 'kubectl create serviceaccount'. It's also useful to review Active Directory logs if accounts are being created within a domain context. |
| Key Indicators | Look for Event ID 4720 in Windows Security logs indicating a new local user account. On macOS, the presence of 'dscl -create' in system logs. For network devices, CLI logs showing 'username' commands or new account entries. In Kubernetes logs, watch for 'create serviceaccount' actions. Also, unexpected account creations during non-business hours or from unusual IP addresses can be key indicators. |
| Questions for Analysis | What time was the account created? Does the username follow standard naming conventions? Was the account creation associated with known administrator or service accounts? Is there evidence of remote access activity before or after the account creation? Are there any follow-up actions executed by the new account, such as privilege escalations or logins? |
| Decision for Escalation | Escalate if the new account was created by a non-administrative account or if the creation was inconsistent with normal operational patterns (e.g., unusual times, locations, or frequency). Also, escalate if subsequent suspicious activity is linked to the newly created account. |
| Additional Analysis Steps for L1 | Verify the legitimacy of the username with asset owners or administrators. Check endpoint or network logs for any associated suspicious behavior after the account's creation. Cross-reference other security alerts or incidents around the same timeframe. Validate the system where the account was created against known authorized access policies. |
| T2 Analyst Actions | Conduct a deep dive analysis into account creation circumstances and correlating events. Check for unauthorized or anomalous access patterns post-account creation. Review historical logs for repeated account creation attempts or patterns. Evaluate any lateral movement or privilege escalation linked to the account. |
| Containment and Further Analysis | Disable the suspicious account immediately to prevent further unauthorized access. Perform a full endpoint assessment on the host where the account was created. Ensure comprehensive review and cleanup of any unauthorized changes. Consider implementing stricter monitoring and access controls to prevent future unauthorized account creations. |
