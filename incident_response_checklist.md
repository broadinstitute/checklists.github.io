# Incident Response Checklist
For the engineer managing a production incident.

## During the incident
- <input type='checkbox'> `immediately` **If the incident originates in PagerDuty, acknowledge the event in PagerDuty and click *More Actions* -> *Create JIRA Issue* to create a ticket on the [Production Board](https://broadworkbench.atlassian.net/secure/RapidBoard.jspa?rapidView=15&projectKey=PROD&selectedIssue=PROD-324)**
    - This will create a Jira bug that includes some metadata about the incident, including start-time.  Update the summary and description as needed and assign to yourself.
    - If the incident does NOT originate in PagerDuty, confirm that a Jira bug has been made or create one. 
- <input type='checkbox'> `immediately` **Move the Jira bug to "In Progress"**
- <input type='checkbox'> `immediately` **Mention in #workbench-resiliance that you are investigating the issue.** 
- <input type='checkbox'> **Notify users of the incident**
    - If it impacts many users:
        - `4 hrs` Daytime: Confirm that a support specialist is aware of the issue (slack #dsde-comms or @dspsupportteam in #workbench-resilience) and can put up a FireCloud/Terra [Service Incident](https://broadinstitute.zendesk.com/hc/en-us/sections/360003692231-Service-Notifications) and banner. Provide the Jira ticket and a description of the user impact.
        - `8 hrs` Off-hours: [Follow this communication playbook to put up an initial banner.](https://docs.google.com/document/d/1E2qSIQECBBS0daWa_VXAOprdV5H_zvirgryTbxbPTDg/edit)
    - Impacts a single user (the user will need to be directly contacted)
        - `8 hrs` Daytime: contact a support specialist for assistance (slack #dsde-comms or @dspsupportteam in #workbench-resilience). 
        - `12 hrs` Off-hours: Contact the user and cc support@terra.bio . The email should explain the time the issue occurred, how the issue is impacting the user, and any relevant Terra details (workspace/submission/notebook/etc.) The Frontline support team will follow up with the user the next work day to answer any further questions.
    - Confirm that the "Users Informed" field has been updated on the Jira bug.
- <input type='checkbox'> `12 hrs` **Oversee the remediation of the issue, returning the affected systems to normal.**  Follow steps in the [General Troubleshooting Playbook](https://docs.google.com/document/d/1KUdZBrnedzCCYQTNNmUCn_NVgTvfVKby_dyU7Laq5g0/edit#).  
    - Note that "remediation" means that the system is back "up" and affected users are unblocked, not necessarily that the underlying cause has been fixed.
    - If there are additional actions to address root cause, track them as tickets on the appropriate Jira board.

## After the incident
- <input type='checkbox'> `immediately` **Move the Jira bug to "Remediated"**
    - This will automatically create an epic to track post mortem actions and link the bug.  Link any additional remediation tasks as issues in the epic. 
    - From here, scrum masters will begin to schedule the post-mortem
- <input type='checkbox'> `immediately` **If a banner has been put up, confirm that a support specialist can take down the banners and update the Service Incident.**
- <input type='checkbox'> `1-2 days` **Update the Jira bug with relevant information**
    - Update components/services impacted
    - Update Description:
        - Update what was the issue
        - Enter how it was resolved
        - Gather logs
    - Set Origin: Automated alerting systems such as New Relic or human (Support team, CS)
- <input type='checkbox'> `1-2 days` **Create a [new post mortem](https://broadworkbench.atlassian.net/wiki/spaces/AP/pages/702021656/Post+Mortems) from the Confluence template.**
    - Set the incident summary as `description`
    - To the best of your ability, fill out `1. What happened(timeline)?` and `3. Who was involved?`
    - Link the post mortem to the new epic as a Confluence page (the drop arrow besides "Link Issue")
