# Incident Response Checklist
For on-call engineers

## During an incident
- <input type='checkbox'> **Acknowledge the event in PagerDuty**
- <input type='checkbox'> **Open a Jira ticket on the [Production Board](https://broadworkbench.atlassian.net/secure/RapidBoard.jspa?rapidView=15&projectKey=PROD&selectedIssue=PROD-324)**
    - Create a new ticket with fields summary, description, CLIA Impact (TBD if not known).  Set severity based on [Terra Support SLA](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit?usp=sharing), defaulting to “Blocker”
    - Assign to yourself if you are investigating the issue
- <input type='checkbox'>**Report in the #workbench-oncall slack channel that you are investigating event**
    - If it impacts many users:
        - Daytime: Confirm that a support specialist is aware of the issue (slack #dsde-comms or @dspsupportteam in #workbench-resilience) and can put up a FireCloud/Terra [Service Incident](https://broadinstitute.zendesk.com/hc/en-us/sections/360003692231-Service-Notifications) and banner. Provide the Jira ticket and a description of the user impact.
        - Off-hours: [Follow this communication playbook to put up an initial banner.](https://docs.google.com/document/d/1E2qSIQECBBS0daWa_VXAOprdV5H_zvirgryTbxbPTDg/edit)
    - Impacts a single user (the user will need to be directly contacted)
        - Daytime: contact a support specialist for assistance (slack #dsde-comms or @dspsupportteam in #workbench-resilience). 
        - Off-hours:  There is no dedicated support schedule. Ultimately, the email to the user should explain the impact to them, the time it occurred, what workspace/submission/ was impacted, ways to remediate the issue, and how we are working to prevent this in the future. The tone should be apologetic and helpful.
- <input type='checkbox'> **Oversee the remediation of the issue, returning the affected systems to normal.**  Follow steps in the General Troubleshooting Playbook.

## After the incident
- <input type='checkbox'> **Update the Jira ticket with relevant information**
    - Update CLIA Impact*: 
        - Downtime duration
        - Impact on the system. 
    - Set Component: Component/ Service that is impacted.
    - Update Description:
        - Update what was the issue
        - Enter how it was resolved
        - Link to PagerDuty alert if it was an automated alert. Or link to slack message that first indicated the issue. This is to get as close to time of incident for engineers that will follow up the investigation and dig into the logs.
        - Gather logs
    - Set Origin: Automated alerting systems such as New Relic or human (Support team, CS)
- <input type='checkbox'> **Move the ticket to "Remediated"**
- <input type='checkbox'> **If a banner has been put up, confirm that a support specialist can take down the banners and update the Service Incident.**
- <input type='checkbox'> **Create a post-mortem notes in the [Post Mortems Folder](https://drive.google.com/drive/u/0/folders/1-tGmN1KZqDIBePxc-ZleNv4meXoyA9ET) using the [template](https://docs.google.com/document/d/1BLtWVeWrzCpfEZSjSlSnTeUsJSB64rEd2WkSUgP7FZc/edit)**
    - Use the date and a summary of the incident as the title
    - Fill out a draft of the incident timeline, to the best of your ability
    - Include a list of people who were heavily involved in remediation and should be present at the post-mortem
- <input type='checkbox'> **Create an epic to track post-mortem actions and move to "Needs Post-Mortem"**
    - Title it "Post Mortem for ______" (issue summary)
    - Link the incident issue to the epic
    - Include a link to the post-mortem notes in the description

