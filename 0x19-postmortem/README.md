Postmortem: Web Stack Outage on November 13, 2023 (GMT)


Issue Summary:

The web stack experienced an outage from 10:30 AM to 12:15 PM (GMT), impacting the user authentication service. Approximately 25% of users were unable to log in during this period.

Root Cause:

The root cause of the outage was identified as a database connection issue. A misconfiguration in the load balancer resulted in excessive connections, causing the authentication service to become unresponsive.

Timeline:

Detection Time: The issue was detected at 10:30 AM through monitoring alerts indicating a surge in failed authentication attempts.
Actions Taken: The team initiated an investigation, focusing on potential issues with the authentication service. Initial assumptions suggested a code-level problem.
Misleading Paths: Investigations initially led the team to examine the authentication service codebase, diverting attention from the underlying database connection issue.
Escalation: Recognizing the need for database expertise, the incident was escalated to the database administration team.
Resolution: The issue was resolved by reconfiguring the load balancer to manage database connections more efficiently.
Root Cause and Resolution:

Cause: The root cause was a misconfiguration in the load balancer, leading to an excessive number of database connections that overwhelmed the authentication service.
Resolution: To address the issue, the team reconfigured the load balancer to implement connection pooling, ensuring a more stable and efficient distribution of connections.
Corrective and Preventative Measures:

Improvements/Fixes:

Implement regular audits of load balancer configurations to identify potential issues.
Enhance monitoring alerts to promptly detect abnormal patterns in authentication attempts.
Tasks to Address the Issue:

Conduct a thorough review of load balancer configurations across all services.
Update documentation to include best practices for load balancer configuration to prevent future misconfigurations.
Schedule regular training sessions for the operations team to stay updated on the latest load balancing techniques.

Conclusion:

This postmortem sheds light on the outage's timeline, root cause, and the corrective actions taken. By implementing the identified improvements and fixes, we aim to fortify our web stack against similar incidents, ensuring a more resilient and reliable user authentication service.


