# Incident Response Checklist
For the engineer managing a production incident. Visit [broad.io/tir](https://broad.io/tir) for the full list of Terra Incident Response documentation.

## During the incident
- <input type='checkbox'> <span style="color:red">`immediately`</span> **If the incident originates in PagerDuty, acknowledge the event in PagerDuty and click *More Actions* -> *Create JIRA Issue* to create a ticket on the [Production Board](https://broadworkbench.atlassian.net/secure/RapidBoard.jspa?rapidView=88&projectKey=PROD)**
    - This will create a Jira bug that includes incident start-time.  Update the summary and description as needed and assign to yourself.
    - If the incident does NOT originate in PagerDuty, confirm that a Jira bug has been made or create one. 
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Change the Jira bug priority to Critical or Blocker based on our [SLA definitions](https://docs.google.com/spreadsheets/d/1Qcfve-nHlS0Udq31nZlfwBDjguhsJ8sxm0Q7RqfZM8o/edit#gid=0)**
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Move the Jira bug to "In Progress" status**
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Mention in the #workbench-resilience ticket thread that you are investigating the issue.** 
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Notify users of the incident**
    - Impacts multiple users:
        - <span style="color:darkorange">`4 hrs`</span> Daytime: Confirm that a support specialist is aware of the issue (slack @terrasupport in the JIRA ticket thread in #workbench-resilience). The support specialist can set up the necessary user communications (article/banner/etc.). Provide the support specialist with information about when the issue started, which services are affected, how users are impacted, and if there are any known workarounds.
        - <span style="color:darkorange">`8 hrs`</span> Off-hours: Put up a banner in Terra.
            1. Connect to VPN (either split or non-split) using Cisco AnyConnect or your VPN client of choice
            2. Navigate to https://fcprod-jenkins.dsp-techops.broadinstitute.org and log in
            3. Navigate to the [terra-service-banner-add](https://fcprod-jenkins.dsp-techops.broadinstitute.org/job/terra-service-banner-add/) job. Click on "Build With Parameters" on the left-hand side. You will see a screen with free text fields and information about how to fill in banner details.       
    - Impacts a single user (the user will need to be directly contacted)
        - <span style="color:darkorange">`8 hrs`</span> Daytime: contact a support specialist for assistance (slack @terrasupport in the JIRA ticket thread in #workbench-resilience). 
        - <span style="color:gold">`12 hrs`</span> Off-hours: Email the user and cc support@terra.bio . The email should explain the time the issue occurred, how the issue is impacting the user, and any relevant Terra details (workspace/submission/notebook/etc.) The Frontline support team will follow up with the user the next work day to answer any further questions.
- <input type='checkbox'><span style="color:red">`immediately`</span> **Set the _Users Informed_ field on the Jira bug to "Yes".**
- <input type='checkbox'> <span style="color:darkorange">`12 hrs`</span> (Blocker) <span style="color:gold">`48 hrs`</span> (Critical) **Oversee the remediation of the issue, returning the affected systems to normal.**  Follow steps in the [General Troubleshooting Playbook](https://docs.google.com/document/d/1KUdZBrnedzCCYQTNNmUCn_NVgTvfVKby_dyU7Laq5g0/edit#).
    - Note that "remediation" means that the system is back "up" and affected users are unblocked, not necessarily that the underlying cause has been fixed.
    - If there are additional actions to address root cause, track them as tickets on the appropriate Jira board.
- <input type='checkbox'> **If the investigation must be passed between daytime and off-hours engineers, ensure all relevant information is captured in JIRA/Slack so the handoff is as smooth as possible.**

## After the incident
- <input type='checkbox'> <span style="color:red">`immediately`</span> **Move the Jira bug to "Remediated" status**
    - This will automatically create an Epic to track incident review actions and link the Bug.
    - Link any additional remediation tasks as issues in the **Bug** ticket. 
- <input type='checkbox'> <span style="color:red">`immediately`</span> **If a banner has been put up, confirm that it gets taken down.** 
   - During off-hours: Take down the banner by running the [terra-service-banner-clear](https://fcprod-jenkins.dsp-techops.broadinstitute.org/job/terra-service-banner-clear/) job if there is only one banner displaying on the platform. Use the [terra-service-banner-remove](https://fcprod-jenkins.dsp-techops.broadinstitute.org/job/terra-service-banner-remove/) job if more than one banner is up. See the [Terra Multi-Banner Readme](https://docs.google.com/document/d/16Av62pb1Dk6FiwqvhbcNE1hWq9WdLcP9iWvK-lZQmd0/edit#) for more details about these jobs.
- <input type='checkbox'> <span style="color:red">`immediately`</span> **If the incident originated from PagerDuty, confirm that the PagerDuty incident was resolved or resolve it manually**
- <input type='checkbox'> <span style="color:gold">`1-2 days`</span> **Update the Jira bug with relevant information**
    - Update the ***DateTime Issue Introduced*** field with the time the issue was introduced to production. If unknown, use the time of the first user report.
    - Update the ***DateTime Incident Declared*** field with the time we declared the incident.
    - Update the ***Teams*** field with the appropriate team for the service affected.
    - Update components/services impacted
    - Update Description:
        - Update what was the issue
        - Enter how it was resolved
        - Gather logs
    - Set Origin: Automated alerting systems such as New Relic or human (Support team, CS)
- <input type='checkbox'> <span style="color:gold">`1-2 days`</span> **Create a [new incident review notes page](https://broadworkbench.atlassian.net/wiki/spaces/AP/pages/702021656/Post+Mortems) from the Confluence template.**
    - Set the incident summary as `description`
    - To the best of your ability, fill out `1. What happened(timeline)?` and `3. Who was involved?`
    - Link the incident review to the new epic as a Confluence page (the drop arrow besides "Link Issue")
