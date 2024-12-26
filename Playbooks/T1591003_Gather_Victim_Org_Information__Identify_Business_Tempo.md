# Gather_Victim_Org_Information:_Identify_Business_Tempo - T1591003

| Column Name | Value |
|-------------|-------|
| MITRE Tactic | Reconnaissance |
| MITRE TTP | T1591.003 |
| MITRE Sub-TTP | T1591.003 |
| Name | Gather Victim Org Information: Identify Business Tempo |
| Log Sources to Investigate | Investigate employee email logs for unusual requests or queries about operational hours, especially from unknown or external sources. Review social media monitoring tools for mentions or posts about the company's business hours or operational schedules. Examine web access logs for patterns of access that coincide with business hours or operational events (such as spikes in access at the end of business hours). |
| Key Indicators | Unusual frequency of external queries about operational details. Social media posts or discussions about company business timings not shared officially by the company. Access attempts or logins during non-working hours from atypical sources or locations. |
| Questions for Analysis | Are external emails requesting information about business hours or operational schedules legitimate or expected? Do social media mentions align with official communications from the organization? Are there repeated access attempts during off-hours, and if so, are they aligned with known employee work patterns? |
| Decision for Escalation | Escalate to Tier 2 if there are confirmed instances of suspicious external queries about business operations, such as an unusual pattern in logins or access attempts during off-hours, especially if this activity is from unfamiliar or suspicious IP addresses. |
| Additional Analysis Steps for L1 | Verify the sender's legitimacy if email requests for business schedules are received. Cross-reference social media mentions with company announcements. Check historical access logs for similar patterns to identify whether this behavior is consistent or an anomaly. |
| T2 Analyst Actions | Deep dive into network traffic data to trace the source of suspicious activity. Conduct open-source intelligence (OSINT) to identify if other organizations are experiencing similar reconnaissance activities. Engage with internal teams to verify if any legitimate business processes could explain the patterns observed. |
| Containment and Further Analysis | If unusual patterns are deemed a credible reconnaissance attempt, restrict access from identified suspicious sources. Communicate with affected departments to raise awareness. Implement tighter monitoring controls for network activities related to business operations data. Initiate a threat hunt for other potential compromises that may have been aided by this reconnaissance. |
