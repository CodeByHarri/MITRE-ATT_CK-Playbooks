# Escape_to_Host - T1611

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Privilege Escalation |
| MITRE TTP | T1611 |
| MITRE Sub-TTP | T1611 |
| Name | Escape to Host |
| Log Sources to Investigate | Review logs from container orchestration platforms (such as Kubernetes audit logs), container runtime logs (e.g., Docker daemon logs), and host operating system logs for unexpected activities. Monitor configuration management data for changes to container settings, especially those involving bind mounts and privilege escalation. Examine application logs that might show unexpected privilege usage or unsanctioned access to host-level resources. |
| Key Indicators | Unusual container configurations with host filesystem bind mounts, privileged container starts, and execution of unexpected host-level commands or utilities from within containers. Alerts for system calls like 'unshare' and 'keyctl' used in unexpected contexts. Access attempts to 'docker.sock' or other sensitive host management sockets from within a container. |
| Questions for Analysis | Was there any recently deployed container with bind mounts of the host filesystem? Were any containers running with elevated privileges? Are there logs of system calls 'unshare' or 'keyctl' that are not typically used by the applications? Was there unauthorized access or modification noted to 'docker.sock'? |
| Decision for Escalation | Escalate if there are confirmed indications of container escape or unauthorized access attempts to the host, such as evidence of host filesystem mounts, execution of host-level control utilities, or exploit attempts against host management sockets. Additionally, escalate if rogue privileged container operations are confirmed. |
| Additional Analysis Steps for L1 | Validate the container configuration settings against organizational policies. Check for any changes in permissions or configurations of host resources associated with containers. Correlate recent changes in configuration management systems related to containers. |
| T2 Analyst Actions | Conduct deeper forensic analysis on affected hosts for signs of unauthorized access or lateral movement. Evaluate any discovered artifacts or logs for signs of tampering or malicious payloads. Work with IT to check current system and container vulnerability status to rule out recently disclosed exploits. |
| Containment and Further Analysis | Immediately isolate any suspicious containers. Revert any unauthorized changes to container or host configurations. Patch any vulnerabilities within the container and host environments. Review access controls and audit privileges assigned to application containers. Conduct a thorough audit of container images to ensure they have not been tampered with, and implement enhanced monitoring for future container and host interactions. |
