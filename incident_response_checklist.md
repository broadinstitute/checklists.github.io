# Incident Response Checklist
For on-call engineers

## During an incident
- <input type='checkbox'> **Acknowledge the event in PagerDuty**
- <input type='checkbox'> **From the PagerDuty incident, click *More Actions* -> *Create JIRA Issue* to create a ticket on the [Production Board](https://broadworkbench.atlassian.net/secure/RapidBoard.jspa?rapidView=15&projectKey=PROD&selectedIssue=PROD-324)**
    - This will create a Jira ticket that includes some metadata about the incident, including start-time.  Update the summary and description as needed.
    - Assign to yourself if you are investigating the issue
- <input type='checkbox'> **Report in the #workbench-oncall slack channel that you are investigating event**
    - If it impacts many users:
        - Daytime: Confirm that a support specialist is aware of the issue (slack #dsde-comms or @dspsupportteam in #workbench-resilience) and can put up a FireCloud/Terra [Service Incident](https://broadinstitute.zendesk.com/hc/en-us/sections/360003692231-Service-Notifications) and banner. Provide the Jira ticket and a description of the user impact.
        - Off-hours: [Follow this communication playbook to put up an initial banner.](https://docs.google.com/document/d/1E2qSIQECBBS0daWa_VXAOprdV5H_zvirgryTbxbPTDg/edit)
    - Impacts a single user (the user will need to be directly contacted)
        - Daytime: contact a support specialist for assistance (slack #dsde-comms or @dspsupportteam in #workbench-resilience). 
        - Off-hours: Contact the user and cc support@terra.bio . The email should explain the time the issue occurred, how the issue is impacting the user, and any relevant Terra details (workspace/submission/notebook/etc.) The Frontline support team will follow up with the user the next work day to answer any further questions.
    - Confirm that the "Users Informed" field has been updated on the Jira bug.
- <input type='checkbox'> **Oversee the remediation of the issue, returning the affected systems to normal.**  Follow steps in the [General Troubleshooting Playbook](https://docs.google.com/document/d/1KUdZBrnedzCCYQTNNmUCn_NVgTvfVKby_dyU7Laq5g0/edit#).  
    - Note that "remediation" means that the system is back "up" and affected users are unblocked, not necessarily that the underlying cause has been fixed.
    - If there are additional actions to address root cause, track them as tickets on the appropriate Jira board.

## After the incident
- <input type='checkbox'> **Move the Jira bug to "Remediated"**
    - This will automatically create an epic to track post mortem actions and link the bug.  Link any additional remediation tasks as issues in the epic. 
- <input type='checkbox'> **If a banner has been put up, confirm that a support specialist can take down the banners and update the Service Incident.**
- <input type='checkbox'> **Update the Jira bug with relevant information**
    - Update components/services impacted
    - Update Description:
        - Update what was the issue
        - Enter how it was resolved
        - Gather logs
    - Set Origin: Automated alerting systems such as New Relic or human (Support team, CS)
- <input type='checkbox'> **Create a [new post mortem](https://broadworkbench.atlassian.net/wiki/spaces/AP/pages/702021656/Post+Mortems) from the Confluence template.
    - Set the incident summary as `description`
    - To the best of your ability, fill out `1. What happened(timeline)?` and `3. Who was involved?`
    - Link the post mortem to the new epic as a Confluence page (the drop arrow besides "Link Issue")
