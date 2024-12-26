# Create_or_Modify_System_Process:_Container_Service - T1543005

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Persistence, Privilege Escalation |
| MITRE TTP | T1543.005 |
| MITRE Sub-TTP | T1543.005 |
| Name | Create or Modify System Process: Container Service |
| Log Sources to Investigate | Monitor container orchestration logs such as Kubernetes API server logs, Docker daemon logs, and Podman logs. Also, observe systemd service logs on hosts running containers. Pay attention to logs showing changes in container configurations, such as 'docker run' commands with unusual flags. Review Kubernetes audit logs for DaemonSet and Pod deployment or modification activities. |
| Key Indicators | Look for 'docker run' or 'podman run' commands with the 'restart=always' directive, especially if issued by non-administrative users. Examine any changes to DaemonSet configurations in Kubernetes allowing deployment across nodes. Identify the use of 'nodeSelector' or 'nodeName' fields targeting specific nodes. Suspicious systemd service configuration changes for containers should also be noted. |
| Questions for Analysis | Did the container configuration change occur outside of planned maintenance windows or by unauthorized users? Are there signs of lateral movement or privilege escalation, such as access to sensitive resources or deployment of unauthorized DaemonSets? Is there unexpected use of 'nodeSelector' to deploy pods on critical nodes? |
| Decision for Escalation | Escalate if unauthorized changes to container configurations are detected, if suspicious or unfamiliar users engage in these actions, or if there's evidence suggesting privilege escalation or lateral movement. Any indications of containers configured to run at boot through systemd should also be escalated. |
| Additional Analysis Steps for L1 | Verify the identity and permissions of users making configuration changes. Cross-reference change times with scheduled activities. Look for other indicators of compromise, such as anomalous network traffic from the impacted container. Confirm whether the involved containers have access to sensitive data or systems. |
| T2 Analyst Actions | Conduct a deeper investigation on the user's activity across various logs to identify additional malicious behavior. Inspect the integrity and contents of the involved containers and images for backdoors or unexpected applications. Evaluate the security settings of the Kubernetes or container orchestration environments. |
| Containment and Further Analysis | Quarantine affected containers and nodes, apply patches or updates, and change affected accounts' privileges. Conduct a full audit of all container configurations and deployments for further unauthorized changes. Implement monitoring for recurrence and assess the environment's security posture to prevent future occurrences. |
