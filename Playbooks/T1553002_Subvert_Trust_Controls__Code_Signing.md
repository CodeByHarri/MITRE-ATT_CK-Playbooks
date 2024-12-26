# Subvert_Trust_Controls:_Code_Signing - T1553002

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Defense Evasion |
| MITRE TTP | T1553.002 |
| MITRE Sub-TTP | T1553.002 |
| Name | Subvert Trust Controls: Code Signing |
| Log Sources to Investigate | Investigate logs from endpoint detection and response (EDR) solutions, which can capture information on executable files, their associated processes, and any code signing details. Security information and event management (SIEM) systems should also be checked for logs related to user authentication, access to code signing infrastructures, and logging from certificate authorities if applicable. Examples include Windows Event Logs (Security event ID 4688 for process creation), macOS Unified Logs, and any logs from antivirus or application whitelisting systems. |
| Key Indicators | Look for newly signed binaries, especially those signed with unexpected or newly issued certificates and those not commonly associated with known developers or vendors. Indicators may include sudden access to private key stores, abnormal code signing activity outside of regular patterns, and mismatches between the binary origination data and the signing certificate details. |
| Questions for Analysis | Is the signing certificate used recently created or modified? Does the certificate originate from a trusted certificate authority? Has the binary in question been observed before, and is it associated with typical business software? Does the executable have any reputation history or previous detection indicators? |
| Decision for Escalation | Escalate if the certificate was not issued by a trusted authority or has an anomalous pattern of behavior such as being used for a file not typically signed by that certificate. A lack of a credible reputation for the file or certificate authority should also prompt escalation. Additionally, any indication of compromised private keys should be escalated. |
| Additional Analysis Steps for L1 | Verify the certificate chain for authenticity and trust. Cross-check the binary's hash against threat intelligence databases to identify any previous associations with malicious activity. Review logs for any recent non-standard access to certificate management systems or anomalies in the creation of new certificates. |
| T2 Analyst Actions | Perform in-depth validation of the certificate's origin and usage history. Analyze behavior and properties of the signed executable in a controlled environment, such as a sandbox, to detect any malicious behavior. Consult with certificate authorities to verify the legitimacy of the certificate, if necessary. |
| Containment and Further Analysis | If confirmed malicious, revoke the certificate if within internal control to do so or notify the certificate authority immediately. Quarantine affected systems or binaries to prevent further execution. Enhance monitoring for similar code signing activities and ensure that access to certificate management systems is secured and logged. Review and strengthen policies around code signing and certificate management to prevent future occurrences. |