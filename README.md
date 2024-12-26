# MITRE ATT&CK Playbooks Repository

These playbooks are starting points/ drafts for initial triage.


## Folder Structure

The folder structure is organized as follows:

```
/Playbooks
    /Defense_Evasion
        T1548_Abuse_Elevation_Control_Mechanism.md
    /Privilege_Escalation
        T1548_Abuse_Elevation_Control_Mechanism.md
    /Persistence
        T1568.002_Another_Example.md
    /Execution
        T1568.001_Execution_Playbook.md
    ...
```

### Key Points:

- **Top-Level Folder (`/Markdowns`)**: All the generated Markdown files are stored in the root folder called `Markdowns`.
- **Tactic-Specific Subfolders**: Inside the `Markdowns` folder, each tactic (e.g., `Defense_Evasion`, `Privilege_Escalation`, `Persistence`) has its own subfolder. These subfolders contain the corresponding playbook Markdown files that are relevant to that specific tactic.
    - For example, a playbook associated with the tactic "Privilege Escalation" will be placed in the `Privilege_Escalation` folder.
    - Multiple tactics in the same row will ensure that the playbook is placed in the folder corresponding to each relevant tactic.
- **Markdown Files**: Each Markdown file is named using a combination of the MITRE TTP identifier (e.g., `T1548`) and the playbook name (e.g., `Abuse_Elevation_Control_Mechanism`). These files contain the details of the playbook, including relevant analysis steps, indicators, and actions for specific TTPs.

### File Naming Convention

Each file is named using the following format:

```
{MITRE_TTP}_{Name}.md
```

- **`MITRE_TTP`**: The unique identifier for the MITRE TTP (e.g., `T1548`).
- **`Name`**: The name or description of the playbook (e.g., `Abuse_Elevation_Control_Mechanism`).

## 🔎 **Playbook Format**

Each playbook is structured as follows:

| **MITRE Tactic**        | **MITRE TTP**       | **MITRE Sub-TTP** | **Name**             | **Log Sources to Investigate**                                                                                                                                                                                                                             | **Key Indicators**                                                                                                                                                                                                 | **Questions for Analysis**                                                                                                                                                                                                                             | **Decision for Escalation**                                                                                                                                                                                                                                           | **Additional Analysis Steps for L1**                                                                                                                                                                                                                                                                                              | **T2 Analyst Actions**                                                                                                                                                                                                                                                                                                                                  | **Containment and Further Analysis**                                                                                                                                                                                                                             |
|--------------------------|---------------------|--------------------|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|

- **MITRE Tactic:** The specific tactic from the ATT&CK Framework (e.g., Reconnaissance, Credential Access).
- **MITRE TTP:** The associated technique ID (e.g., `T1010` for Application Window Discovery).
- **MITRE Sub-TTP:** The sub-technique ID if applicable (e.g., `T1010.001`).
- **Name:** A descriptive name for the TTP.
- **Log Sources to Investigate:** Relevant telemetry sources (e.g., EDR, DNS logs, firewall logs).
- **Key Indicators:** Observable indicators (e.g., unusual processes, abnormal traffic patterns).
- **Questions for Analysis:** Suggested questions to determine if an alert is benign or malicious.
- **Decision for Escalation:** Clear criteria for escalating alerts to higher-tier analysts.
- **Additional Analysis Steps for L1:** Actions for Tier 1 analysts to validate and contextualize detections.
- **T2 Analyst Actions:** Specific tasks for Tier 2 analysts, including containment and advanced analysis.
- **Containment and Further Analysis:** Detailed steps for mitigation and investigation.
