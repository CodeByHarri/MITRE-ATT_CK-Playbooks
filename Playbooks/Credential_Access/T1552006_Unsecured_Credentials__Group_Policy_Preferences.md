# Unsecured_Credentials:_Group_Policy_Preferences - T1552006

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Credential Access |
| MITRE TTP | T1552.006 |
| MITRE Sub-TTP | T1552.006 |
| Name | Unsecured Credentials: Group Policy Preferences |
| Log Sources to Investigate | Investigate logs from file access monitoring on domain controllers, especially from the SYSVOL directory. Look for logs indicating script execution or file transfers involving GPP XML files. Access logs for tools like Metasploit or PowerShell might also provide relevant information. |
| Key Indicators | 1. Access to SYSVOL directory, especially *.xml files, by non-administrative users.<br>2. Use of known tools/scripts such as Metasploit, Get-GPPPassword, or gpprefdecrypt.py.<br>3. Abnormal file enumeration commands such as 'dir /s *.xml'. 4. Unusual decryption activity, possibly linked to AES key usage. |
| Questions for Analysis | 1. Has the user accessing the SYSVOL share been involved in previous suspicious activities?<br>2. Is there any legitimate reason for this user to access Group Policy Preference (GPP) XML files?<br>3. Are there concurrent access attempts from the same user/ip at different locations? 4. Are there any other anomalies detected in the logs around the same time? |
| Decision for Escalation | Escalate to Tier 2 if: 1. The user accessing the GPP XML files is unauthorized or their actions cannot be justified.<br>2. There are additional signs of lateral movement or credential dumping in conjunction with SYSVOL access.<br>3. Any use of decryption tools or Metasploit modules is detected. |
| Additional Analysis Steps for L1 | 1. Verify the user's role and access requirements with SYSVOL.<br>2. Review past logs for previous access attempts to GPP XML files by the same user.<br>3. Check for concurrent suspicious activities in network or endpoint logs. 4. Confirm whether detected tools/scripts are whitelisted or part of ongoing IT operations. |
| T2 Analyst Actions | 1. Conduct a deeper investigation into the user's activities around the time of detection.<br>2. Analyze the broader network activity for lateral movement or additional pivot points.<br>3. Review the access permissions for SYSVOL and ensure compliance with least privilege principles. 4. Validate if the AES decryption tool or scripts usage was legitimate. |
| Containment and Further Analysis | 1. Implement immediate access restrictions if unauthorized access is confirmed.<br>2. Conduct a full security audit of GPP settings and credentials to ensure no other vectors are exposed.<br>3. Change potentially compromised credentials and enforce strong password policies. 4. Review domain controller logs for potential exfiltration or privilege escalation attempts. |
