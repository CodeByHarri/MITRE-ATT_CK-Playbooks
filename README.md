# MITRE ATT&CK Playbooks Repository

These playbooks serve as **drafts** and starting points for **initial triage**. They are not intended to be final, out-of-the-box solutions but should be adapted to fit the specific practices, procedures, and workflows of the Security Operations Center (SOC) using them.

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

## 🛠️ **Usefulness for SOC L1/L2 Triaging**

These playbooks are primarily designed to assist **SOC L1 and L2 analysts** with the initial triage, validation, and escalation processes in the event of potential security incidents.

- **For L1 Analysts**: These playbooks provide clear and structured guidance on how to investigate specific TTPs. L1 analysts can use these to follow a predefined set of steps to determine whether an alert is benign or malicious, significantly reducing the time spent on repetitive decision-making processes. They will know which logs to examine, which indicators to look for, and the types of questions to ask in their analysis.
  
- **For L2 Analysts**: Once an alert has been escalated to L2, these playbooks offer detailed instructions for a deeper investigation, including advanced analysis steps and containment actions. By following the playbooks, L2 analysts can validate findings, correlate activities across multiple data sources, and take necessary actions to mitigate threats, such as isolating compromised systems or performing memory analysis.

- **Where General Playbooks Aren’t Available**: These playbooks are especially useful in scenarios where a general-purpose playbook or response procedure may not exist. They provide targeted guidance for specific tactics and techniques outlined in the MITRE ATT&CK framework, ensuring that analysts can proceed with confidence even when there is no pre-built, generic playbook available. This allows the SOC team to handle emerging threats and novel attack techniques more effectively.

### **Adaptation to SOC Practices**

**Important**: These playbooks are **drafts** and **starting points**. They should be reviewed and customized to align with the specific workflows, tools, and processes of the SOC using them. SOC teams should adapt these playbooks to their internal standards and infrastructure, ensuring that they match the particular context and capabilities of their environment.

For example:
- The **Log Sources to Investigate** section may need to be adjusted to reflect the specific tools or log sources available in your SOC environment (e.g., endpoint detection tools, firewalls, network monitoring).
- The **Additional Analysis Steps** and **Containment Actions** should be tailored to the organization's specific policies, response protocols, and available resources.

By adapting these playbooks, SOC teams can ensure they are aligned with their internal operational procedures and best practices.
